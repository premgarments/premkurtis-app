# Prem Kurtis Android App – APK kaise banayein

Yeh app www.premkurtis.com ko ek asli Android app ki tarah kholta hai (WebView).
Website me jo bhi badlav karenge, app me apne aap dikhega – app dobara banane ki zaroorat nahi.

## Isme kya-kya chalta hai
- Poora catalogue, size-wise quantity, "Prepare WhatsApp Order"
- WhatsApp / call / UPI links apne app me khulte hain
- Photo / file upload (handwritten order photo, LR upload)
- Image Download (Downloads folder me)
- Neeche kheench kar refresh, back button, loading bar
- Internet na ho to "Dobara koshish karein" page
- Admin pages (order-report, status.php) bhi isi app me khulte hain (same login)

## Tarika 1 – Android Studio (computer par)
1. https://developer.android.com/studio se Android Studio install karein.
2. Android Studio > Open > `PremKurtisApp` folder chunein. Gradle sync hone dein (pehli baar thoda time lagta hai).
3. Menu: Build > Build Bundle(s)/APK(s) > Build APK(s).
4. APK yahan milega: `app/build/outputs/apk/debug/app-debug.apk`
5. APK ko WhatsApp/Drive se phone par bhejein, install karein ("Unknown source" allow karna padega).

## Tarika 2 – bina Android Studio ke (GitHub se)
1. github.com par free account banayein, ek naya private repository banayein.
2. Is folder ki saari files (`.github` folder samet) us repository me upload karein.
3. Repository > Actions > "Build APK" > Run workflow.
4. 5–6 minute baad usi page par `PremKurtis-apk` download hoga – zip kholein, andar app-debug.apk hai.

## Play Store par daalna ho to
Debug APK sirf install/test ke liye hai. Play Store ke liye signed release (AAB) chahiye:
Android Studio > Build > Generate Signed Bundle / APK. Keystore file aur uska password
kahin safe rakhein – kho gaya to app update nahi ho payega.

## Dhyan dene wali baatein
- **"Continue with Google" login**: Google apne rules ki wajah se app ke andar (WebView) Google login
  block karta hai. Customers "LOGIN & SEND ORDER" ya "ORDER WITHOUT LOGIN" use kar sakte hain.
  Agar Google login zaroori hai to batayiye, uska alag tareeka (Chrome Custom Tab) jodna padega.
- App ka naam: `app/src/main/res/values/strings.xml`
- Icon badalna ho: `app/src/main/res/mipmap-*` me `ic_launcher.png` badal dein (`icon-512.png` Play Store ke liye hai).
- Website ka address badalna ho to `MainActivity.java` me `HOME` line badlein.
