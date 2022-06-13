<?xml version='1.1' encoding='UTF-8'?>
<flow-definition plugin="workflow-job@2.36">
  <actions>
    <org.jenkinsci.plugins.pipeline.modeldefinition.actions.DeclarativeJobAction plugin="pipeline-model-definition@1.5.1"/>
    <org.jenkinsci.plugins.pipeline.modeldefinition.actions.DeclarativeJobPropertyTrackerAction plugin="pipeline-model-definition@1.5.1">
      <jobProperties/>
      <triggers/>
      <parameters/>
      <options/>
    </org.jenkinsci.plugins.pipeline.modeldefinition.actions.DeclarativeJobPropertyTrackerAction>
  </actions>
  <description></description>
  <keepDependencies>false</keepDependencies>
  <properties/>
  <definition class="org.jenkinsci.plugins.workflow.cps.CpsFlowDefinition" plugin="workflow-cps@2.78">
    <script>pipeline {
    agent any
    stages {
        stage(&apos;Beta&apos;) {
            //agent { label &apos;worker 1&apos; }
            steps {
                // Clone package
                in_toto_wrap([&apos;stepName&apos;: &apos;Clone&apos;,
                &apos;keyPath&apos;: &apos;/keys/bob&apos;,
                &apos;transport&apos;: &apos;grafeas+https://grafeas.nyu.wtf/v1beta1/projects/in-toto-grafeas-jenkins/occurrences?noteName=projects/in-toto-grafeas/notes/clone&amp;resourceUri=uri1&apos;]){
                    //sh label: &apos;download-source&apos;, script: &apos;git clone https://github.com/in-toto/demo-project&apos;
                    git &apos;https://github.com/in-toto/demo-project&apos;
                }

                // Create package
                in_toto_wrap([&apos;stepName&apos;: &apos;Package&apos;,
                &apos;keyPath&apos;: &apos;/keys/carl&apos;,
                &apos;transport&apos;: &apos;grafeas+https://grafeas.nyu.wtf/v1beta1/projects/in-toto-grafeas-jenkins/occurrences?noteName=projects/in-toto-grafeas/notes/package&amp;resourceUri=uri2&apos;]){
                    sh label: &apos;compress-for-release&apos;, script: &apos;tar --exclude .git -zcvf demo-project.tar.gz .&apos;
                }
            }
        }
    }
}
</script>
    <sandbox>true</sandbox>
  </definition>
  <triggers/>
  <disabled>false</disabled>
</flow-definition>
