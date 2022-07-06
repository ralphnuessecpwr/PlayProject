node {
  stage ('Checkout')
  {
    // Get the code from the Git repository
    checkout scm
  }

  stage('Git to ISPW Synchronization')
  {
    gitToIspwIntegration app: 'PLAY',
    branchMapping: '''master => STG1, per-commit
      ''',
    connectionId: 'CWC2',
    credentialsId: 'hddrxm0',
    gitCredentialsId: 'GitHub_ralphnuesse',
    gitRepoUrl: 'https://github.com/ralphnuessecpwr/PlayProject.git',
    runtimeConfig: 'isp8',
    stream: 'PLAY',
    ispwConfigPath: './ispwconfig.yml'
  }
}