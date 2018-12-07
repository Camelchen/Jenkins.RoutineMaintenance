node {
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      bat 'IF EXIST Selenium.Framework (rmdir Selenium.Framework /s /q)'
      bat 'git clone https://github.com/Camelchen/Selenium.Framework.git'
  
   }
   stage('Build') {
      bat 'dotnet restore ./Selenium.Framework/Selenium.Framework.sln'
      bat "\"${tool 'MSBuild'}\" ./Selenium.Framework/SolutionName.sln /p:Configuration=Release /p:Platform=\"Any CPU\" "
   }
   stage('Execute') {
      bat 'dotnet ./Selenium.Framework/Selenium.Droid.ColdLoading/bin/Release/netcoreapp2.1/Selenium.Droid.ColdLoading.dll MoneyHub'
   }
   stage('Archive') {
      archive 'Selenium.Droid.ColdLoading/bin/Release/**' 
   }
}
