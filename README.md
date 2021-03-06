<h1>Reusable Flutter Features</h1>

<p>This project saves codes for applications that would be used for various applications such as:</p>
<ul>
<li>Admob Integration</li>
</ul>

<h2>Google Admob</h2>
<p>Google admob application
\b Add your flutter id in the link in your android manifest: </p>

```
<meta-data
            android:name="com.google.android.gms.ads.APPLICATION_ID"
            android:value="your admob id"/>
```

<p>Increase the minimum sdk to 19 and above</p>

```
android{
    defaultConfig{
        minSdkVersion 19
    }
}
```

<p>Add internet permission to your application. This is added after the manifest tag and before the application tag</p>

```
<manifest xlmns:android...>
 ...
 <uses-permission android:name="android.permission.INTERNET" />
 <application ...
</manifest>
```

<p>Import the library for the google mobile admob</p>

```
    import 'package:google_mobile_ads/google_mobile_ads.dart';
```

<p>Initialize the admob in your main file</p>

```
    void main() {
    WidgetsFlutterBinding.ensureInitialized();
    MobileAds.instance.initialize();

    runApp(MyApp());
    }
```

<h3>Banner Ads</h3>
load the banner ad using the code below 'bannerAd.load()' in the initState method and call the banner ad widget using the 'showAd()' function. This is placed in the widget tree.

```
// load the banner ad
void initState{
    bannerAd.load();
}

//start the banner ad
showAd()
```

<h3>Interstitial Ads</h3>
load the Interstitial ad in the initstate function using the 'createInterstitialAd()' and show the interstitial ads using the function 'showInterstitialAd()'. Note the interstitial ad is not a widget and should not be placed within the widget tree. It should rather be put in a button or in an event that should be triggered

```
//load the interstitial Ad
void initState{
    createInterstitialAd();
}

//start the interstitial Ad
showInterstitialAd()
```

<h3>Reward Ads</h3>
loading the reward ads like other ads using the 'createRewardedAd()' function and then show the reward ad using 'showRewardAd()'. The reward ad is also not a widget and should be called on an event

```
//load the reward Ad
void initState{
    createRewardedAd();
}

//start the reward Ad
showRewardedAd();
```

Get result reward value from the rewarded ad using the function 'getReward()'. This returns the value of reward in integers

```
//get value of reward
int rewardValue = getReward()
```

for any of the ads, save the ads.dart file and call all the functions from the file

<h2>Modify company name and App name</h2>
<p>check out the instructions in "features/company_name.txt" to modify the company name and \b checkout instructions in "features/app_name.txt" to change application name\b</p>
unfortunately, the setup for ios application is currently not available

<h2>Flutter wave</h2>

An integration for payment using flutterwave. This is to simplify the process of adding payment to applicaitons

The script for payment is located in the pay.dart file. The script initializes payments and performs all data formating such that the output for the file is either true or false,
true - for a sucessful applicaiton  and
false - for a failed application
The function for payment is the makePayment() function

```
bool payhandler = makePayment(
    context: context, 
    amount: 100, 
    currency: 1, 
    encryptionKey: ENCRYPTION_KEY, 
    publicKey: PUBLIC_KEY, 
    phoneNumber: "PHONE_NUMBER", 
    paymentNarration: "some narration", 
    userName: "YOUR PAYMENT ACCOUNT", 
    userEmail: "EMAIL", 
    paymentTitle: "TITLE OF PAYMENT PAGE"
);
```
