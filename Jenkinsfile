#!groovy

node ( "5.12.4_mingw7.3_x86") {
    withEnv(["PATH+QT=C:\Qt\Tools\mingw730_64\bin;C:\Qt\5.12.4\mingw73_64\bin"]) {
        stage('Get code') {
            echo 'Getting code with Git....'
        }
        stage('Build') {
            sh 'echo "Building...."'
            sh '''
                C:\Qt\5.12.4\mingw73_32\bin\qmake.exe C:\Projects\HelloWorld\HelloWorld.pro -spec win32-g++ "CONFIG+=debug" "CONFIG+=qml_debug" && C:/Qt/Tools/mingw730_32/bin/mingw32-make.exe qmake_all
                mingw32-make.exe -j4
            '''
        }
    }
}