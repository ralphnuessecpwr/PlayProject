node {
  stage ('Checkout')
  {
    // Get the code from the Git repository
    checkout scm
  }

  stage('Git to Code Pipeline Synchronization')
  {
    gitToIspwIntegration app: 'PLAY', 
        branchMapping: 'master => STG1, per-branch', 
        connectionId: 'de2ad7c3-e924-4dc2-84d5-d0c3afd3e756', 
        credentialsId: 'ea48408b-b2be-4810-8f4e-5b5f35977eb1', 
        gitCredentialsId: '67a3fb18-073f-498b-adee-1a3c75192745', 
        gitRepoUrl: 'https://github.com/ralphnuessecpwr/PlayProject.git', 
        ispwConfigPath: './ispwconfig.yml', 
        runtimeConfig: 'ICCGA', 
        stream: 'PLAY', 
        subAppl: 'PLAY'
  }
  stage('Build COde Pipeline Assignment')
  {
    ispwOperation connectionId: 'de2ad7c3-e924-4dc2-84d5-d0c3afd3e756', 
        consoleLogResponseBody: true, 
        credentialsId: '71063193-ee67-4b52-890a-58843f33c183', 
        ispwAction: 'BuildAssignment', 
        ispwRequestBody: 'buildAutomatically = true'
  }  
}