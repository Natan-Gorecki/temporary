pipeline {
  agent any
  stages {
    stage('Clean Workspace') {
      steps {
        cleanWs()
      }
    }

    stage('Checkout SCM') {
      steps {
        checkout scm
      }
    }


    stage('Checkout External Dependencies')
    {
      when
      {
        expression {
          params.REFRESH_EXTERNAL == 'Refresh dependencies'
        }
      }
      parallel{
        stage('IBPP') {
          steps {
            dir(path: 'C:/Projects/InvenTex/GIT/External/EXT.IBPP') {
              deleteDir()
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/ext.ibpp.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('POCO') {
          steps {
            dir(path: 'C:/Projects/InvenTex/GIT/External/EXT.POCO') {
              deleteDir()
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/ext.poco.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('OPENSSL') {
          steps {
            dir(path: 'C:/Projects/InvenTex/GIT/External/EXT.OPENSSL') {
              deleteDir()
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/ext.openssl.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }
      }
    }

    stage('Checkout InvenTex modules') {
      parallel {
        
        stage('INVENTEX_CORE') {
          when {
            expression {
              return params.'Build INVENTEX_CORE'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }
        
        stage('COMMON') {
          when {
            expression {
              return params.'Build COMMON'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.COMMON') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.common.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }
        
        stage('DATA_CONTROLLER') {
          when {
            expression {
              return params.'Build DATA_CONTROLLER'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.DATA_CONTROLLER') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.data_controller.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('DB_CONNECTOR') {
          when {
            expression {
              return params.'Build DB_CONNECTOR' 
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.DB_CONNECTOR') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.db_connector.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('INI') {
          when {
            expression {
              return params.'Build INI' 
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.INI') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.ini.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('INVOKER') {
          when {
            expression {
              return params.'Build INVOKER' 
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.INVOKER') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.invoker.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('JSON') {
          when {
            expression {
              return params.'Build JSON'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.JSON') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.json.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('ORDER_CREATOR') {
          when {
            expression {
              return params.'Build ORDER_CREATOR'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.ORDER_CREATOR') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.order_creator.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('SETTINGS') {
          when {
            expression {
              return params.'Build SETTINGS'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.SETTINGS') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.settings.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('SVG_GEN') {
          when {
            expression {
              return params.'Build SVG_GEN'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.SVG_GEN') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.svg_gen.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('WEB_CONNECTOR') {
          when {
            expression {
              return params.'Build WEB_CONNECTOR'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.WEB_CONNECTOR') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.web_connector.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('WRAPPER') {
          when {
            expression {
              return params.'Build WRAPPER'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.WRAPPER') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.wrapper.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }

        stage('XML') {
          when {
            expression {
              return params.'Build XML'
            }
          }
          steps {
            dir(path: 'INVENTEX_CORE.XML') {
              git(branch: 'master', url: 'https://inv-bitbucket.bloomdev.pl/scm/invadds/inventex_core.xml.git', credentialsId: '234bc167-3e6f-4435-9ae9-f46a3bb7f576')
            }
          }
        }
        
      }
    }



    //-----------------------------------------------------------------------------------------
    // BUILD
    //-----------------------------------------------------------------------------------------
        
      stage('Build COMMON') {
        when {
          expression {
            return params.'Build COMMON'
          }
        }
        steps {
          dir(path: 'cmake-build') {
            script {
              def static_shared = ""
              def build_number = ""
              

              switch(params.'Output Type') {
                case "Static": static_shared = " "; break
                case "Shared": static_shared = " -DBUILD_SHARED_LIBS=ON"; break
                case "Both": static_shared = " -DBUILD_STATIC_AND_SHARED=ON"; break
              }

              
              switch(params.'Version Number') {
                case "15.0.0": build_number = " -DBUILD_NUMBER=0 "; break
                case "15.0.1": build_number = " -DBUILD_NUMBER=1 "; break
              }


              def cmake_Args = " -A " + params.'Build Architecture' + static_shared +
                build_number + " -DREVISION_NUMBER=${env.BUILD_NUMBER}"


              cmakeBuild installation: 'InSearchPath', cmakeArgs: cmake_Args +
                ''' -DBUILD_INVENTEX_CORE=OFF
                -DBUILD_COMMON=ON
                -DBUILD_DATA_CONTROLLER=OFF
                -DBUILD_DB_CONNECTOR=OFF
                -DBUILD_INI=OFF
                -DBUILD_INVOKER=OFF
                -DBUILD_JSON=OFF
                -DBUILD_ORDER_CREATOR=OFF
                -DBUILD_SETTINGS=OFF
                -DBUILD_SVG_GEN=OFF
                -DBUILD_WEB_CONNECTOR=OFF
                -DBUILD_WRAPPER=OFF
                -DBUILD_XML=OFF''', buildDir: '.', buildType: params.'Build Type', sourceDir: "${WORKSPACE}",
                steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
            }
          }
        }
      }

      stage('Build DB_CONNECTOR') {
        when {
          expression {
            return params.'Build DB_CONNECTOR'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=ON
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build INI') {
        when {
          expression {
            return params.'Build INI'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=ON
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF''', buildDir: '.', sourceDir: "${WORKSPACE}", 
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build JSON') {
        when {
          expression {
            return params.'Build JSON'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=ON
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build XML') {
        when {
          expression {
            return params.'Build XML'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=ON
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build SVG_GEN') {
        when {
          expression {
            return params.'Build SVG_GEN'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=ON
              -DBUILD_INVOKER=OFF''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build INVOKER') {
        when {
          expression {
            return params.'Build INVOKER'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build WEB_CONNECTOR') {
        when {
          expression {
            return params.'Build WEB_CONNECTOR'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF
              -DBUILD_WEB_CONNECTOR=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build ORDER_CREATOR') {
        when {
          expression {
            return params.'Build ORDER_CREATOR'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF
              -DBUILD_ORDER_CREATOR=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build DATA_CONTROLLER') {
        when {
          expression {
            return params.'Build DATA_CONTROLLER'
          }
        }
        steps {
          dir(path: 'cmake-build')
            {
              cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
                -DBUILD_DB_CONNECTOR=OFF
                -DBUILD_INI=OFF
                -DBUILD_JSON=OFF
                -DBUILD_XML=OFF
                -DBUILD_SVG_GEN=OFF
                -DBUILD_INVOKER=OFF
                -DBUILD_ORDER_CREATOR=OFF
                -DBUILD_DATA_CONTROLLER=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
                steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
            }
        }
      }

      stage('Build SETTINGS') {
        when {
          expression {
            return params.'Build SETTINGS'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF
              -DBUILD_ORDER_CREATOR=OFF
              -DBUILD_DATA_CONTROLLER=OFF
              -DBUILD_SETTINGS=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

        
      stage('Build INVENTEX_CORE') {
        when {
          expression {
            return params.'Build INVENTEX_CORE'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF
              -DBUILD_ORDER_CREATOR=OFF
              -DBUILD_DATA_CONTROLLER=OFF
              -DBUILD_SETTINGS=OFF
              -DBUILD_INVENTEX_CORE=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }

      stage('Build WRAPPER') {
        when {
          expression {
            return params.'Build WRAPPER'
          }
        }
        steps {
          dir(path: 'cmake-build')
          {
            cmakeBuild installation: 'InSearchPath', cmakeArgs: '''-DBUILD_COMMON=OFF
              -DBUILD_DB_CONNECTOR=OFF
              -DBUILD_INI=OFF
              -DBUILD_JSON=OFF
              -DBUILD_XML=OFF
              -DBUILD_SVG_GEN=OFF
              -DBUILD_INVOKER=OFF
              -DBUILD_ORDER_CREATOR=OFF
              -DBUILD_DATA_CONTROLLER=OFF
              -DBUILD_SETTINGS=OFF
              -DBUILD_INVENTEX_CORE=OFF
              -DBUILD_WRAPPER=ON''', buildDir: '.', sourceDir: "${WORKSPACE}",
              steps: [[args: "--config ${params.'Build Type'}", withCmake: true]]
          }
        }
      }
      
      stage('Create NuGet package') {
        when {
          expression {
            return params.'Build INVENTEX_CORE' && params.'Build WRAPPER'
          }
        }
        steps {
          sh "nuget pack InvenTexCore.Desktop.nuspec -Version ${params.'Version Number'}.${env.BUILD_NUMBER}"
        }
      }

      stage('Push NuGet package to InvNuget feed')
      {
        when {
          expression {
            return params.'Build INVENTEX_CORE' && params.'Build WRAPPER'
          }
        }
        steps {
          sh "nuget push InvenTexCore.Desktop.${params.'Version Number'}.${env.BUILD_NUMBER}.nupkg " +
          "\$CnKPk?[6VKp@r.c@JJnGPo+J7NuWJXYbKz!]!Kr " +
          "-Source https://inv-nuget.bloomdev.pl/nuget"
        }
      }
     // }
    //}
      /*
      steps {
        echo 'Building...'
        fileExists 'cmake/modules'
        dir(path: 'cmake-build')
        {
          cmakeBuild installation: 'InSearchPath', cmakeArgs: '-A Win32 -DBUILD_STATIC_AND_SHARED=on', buildDir: '.', sourceDir: "${WORKSPACE}", steps: [[withCmake: true]]
        }

        
        
      //cmakeBuild buildType: 'Release', cleanBuild: true, installation: 'InSearchPath', steps: [[withCmake: true]
      //cmakeBuild
      //generator: 'Ninja',
      //buildDir: 'build',
      //sourceDir: 'source',
      //installation: 'InSearchPath',
      //steps: [
      //[args: 'all install', envVars: 'DESTDIR=${WORKSPACE}/artifacts']
      //]
      //}
      }
    }
    */  
    stage('Tests') {
      when {
        expression {
          return 0
        }

      }
      steps {
        echo 'Testing...'
      }
    }

    stage('Deploy') {
      when {
        expression {
          return 1
        }

      }
      steps {
        //bat '''cmake -E INVENTEX_CORE/api C:/Releases/20210205/
        //       cmake -E OUT C:/Releases/20210205/'''
        echo "Deploying..."
      }
    }
    
  }
  options {
    skipDefaultCheckout()
  }
  parameters {
    choice(choices: ['15.0.0', '15.0.1'], description: 'Choose Version Number', name: 'Version Number')

    booleanParam(name:'Build INVENTEX_CORE', defaultValue: false, description: '')
    booleanParam(name:'Build COMMON', defaultValue: false, description: '')
    booleanParam(name:'Build DATA_CONTROLLER', defaultValue: false, description: '')
    booleanParam(name:'Build DB_CONNECTOR', defaultValue: false, description: '')
    booleanParam(name:'Build INI', defaultValue: false, description: '')
    booleanParam(name:'Build INVOKER', defaultValue: false, description: '')
    booleanParam(name:'Build JSON', defaultValue: false, description: '')
    booleanParam(name:'Build ORDER_CREATOR', defaultValue: false, description: '')
    booleanParam(name:'Build SETTINGS', defaultValue: false, description: '')
    booleanParam(name:'Build SVG_GEN', defaultValue: false, description: '')
    booleanParam(name:'Build WEB_CONNECTOR', defaultValue: false, description: '')
    booleanParam(name:'Build WRAPPER', defaultValue: false, description: '')
    booleanParam(name:'Build XML', defaultValue: false, description: '')

    choice(choices: ['Use existing files', 'Refresh dependencies'], description: 'Use external dependencies in InvenTex modules', name: 'REFRESH_EXTERNAL')
    choice(choices: ['Win32', 'x64'], description: 'Choose Build Architecture', name: 'Build Architecture')
    choice(choices: ['Release', 'Debug'], description: 'Choose Build Type', name: 'Build Type')
    choice(choices: ['Static', 'Shared', 'Both'], description: 'Build only static, shared or both types', name: 'Output Type')
  }
}