job('ejemplo2-dsl-job') {
  description('job creado con dsl')
  scm {
    git('https://github.com/LibrerosDavid/jenkins.job.parametrizado.git','main') { node ->
      node / gitConfigName('LibrerosDavid')
      node / gitConfigEmail('j.d.libreroslopez@gmail.com')
    }
  }
  parameters {
    stringParam('nombre', defaultValue = 'popo', description='todo esto es con dsl')
    choiceParam('Opciones', ['1', '2', '3', '4'])
    booleanParam('Animal', false)
  }
  triggers {
    cron('H/7 * * * *')
  }
  steps {
    shell("bash jobscripts.sh")
  }
  publishers {
    mailer('davidunchiha@gmail.com', true, true)
  }
}
