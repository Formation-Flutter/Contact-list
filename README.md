# Display Contact List by Camairetech




Ce projet va vous donner la posibilite de faire un application qui va afficher tous les contact dans votre telephone 

# Usage

Dans ce projet nous allon utilise le package appelle fast_contact, add `fast_contacts` as a [dependency in your `pubspec.yaml` file](https://flutter.io/platform-plugins/).

vous pouvez aussi lander la commande `flutter pub add fast_contact` pour installer le package 

## Permissions  
### Android  
Add the following permission to your AndroidManifest.xml:  
Ajouter cette line dans votre  AndroidManifest.xml le path est android\app\src\main\AndroidManifest.xml:  


une image pour montre cela 
![alt text](https://github.com/[username]/[reponame]/blob/[branch]/image.jpg?raw=true)

```xml  
<uses-permission android:name="android.permission.READ_CONTACTS" />  
```

### iOS
Set the `NSContactsUsageDescription` in your `Info.plist` file  
  
```xml  
<key>NSContactsUsageDescription</key>  
<string>Description of why you need the contacts permission.</string>  
```  

**Note**
`fast_contacts` doesn't handle permissions. Use special plugins (like [permission_handler](https://pub.dartlang.org/packages/permission_handler)) to ask for the permission before accessing contacts.

## Available contact info

- ID
- Display name
- Structured name (prefix, given name, middle name, family name, suffix)
- Emails
- Phones
- Organization (company, department, job description)

## Example

```dart
// Import package  
import 'package:fast_contacts/fast_contacts.dart';  

// Get all contacts
final contacts = await FastContacts.getAllContacts();

// Get first contact's image (thumbnail)
final thumbnail = await FastContacts.getContactImage(contacts[0].id);

// Get first contact's image (full size)
final thumbnail = await FastContacts.getContactImage(contacts[0].id, size: ContactImageSize.fullSize);
```

For a more complete usage example, see `example` project.

## Performance

Loading 1000+ contacts (display name, structured name, phones, emails) at once takes ~200ms on both Android (Samsung Galaxy S8) and iOS (iPhone 8).

![Android: Samsung Galaxy S8](doc/images/android_screenshot.png)

![iOS: iPhone 8](doc/images/ios_screenshot.png)