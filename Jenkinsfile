node {
  stage ('Checkout')
  {
    // Get the code from the Git repository
    checkout scm
  }

  stage('Git to ISPW Synchronization')
  {
    gitToIspwIntegration app: 'PLAY',
    branchMapping: '''master => QA1, per-commit
      ''',
    connectionId: '38e854b0-f7d3-4a8f-bf31-2d8bfac3dbd4',
    credentialsId: 'HDDRXM0',
    gitCredentialsId: 'GitHub_ralphnuesse',
    gitRepoUrl: 'https://github.com/ralphnuessecpwr/PlayProject.git',
    runtimeConfig: 'isp8',
    stream: 'PLAY',
    ispwConfigPath: './ispwconfig.yml'
  }
}