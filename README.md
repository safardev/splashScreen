# splashScreen
Splash screen using bootsplash in React Native
1. install using => npm install --save react-native-bootsplash

2. save logo(png or svg file) in assets/images directory

3. update=> android/app/src/main/java/com/yourapp/MainActivity.kt file
    ->  add these required imports=>
        import android.os.Bundle
        import com.zoontek.rnbootsplash.RNBootSplash
    
    -> then in=> class MainActivity : ReactActivity() {
        override fun onCreate(savedInstanceState: Bundle?) {
            RNBootSplash.init(this, R.style.BootTheme) //  initialize the splash screen
            super.onCreate(savedInstanceState)
            }
        }

4. update=> app.tsx/app.jsx
    -> import BootSplash from 'react-native-bootsplash';
    -> if you are using <NavigationContainer> then =>
        <NavigationContainer onReady={async () => {
            await BootSplash.hide({ fade: true });
                }>
            <RootStack />
        </NavigationContainer>

5. now generate the logo files using - 
    -> npx react-native-bootsplash generate assets/images/logo.png --background="#323333" --assets-output=assets/bootsplash
        #--background="#323333" will change backgrond color of splash screen 
        #--assets-output=assets/bootsplash will save all generated logo files at single location i.e. assets/bootsplash

6. for more options or changes needed, can use => npx react-native-bootsplash generate --help

7. now run the command - npm run to see the magic**
