node('node') {

    def err = null
    currentBuild.result = "SUCCESS"

    try {

      stage 'Checkout'

      stage 'Test'
        env.NODE_ENV = "test"
        print "Environment is : $(env.NODE_ENV)"

        sh 'echo "test environment."'
        sh 'date'

      stage 'Deploy'

        echo 'Deploy images.'

    }

    catch (caughtError) {

      err = caughtError
      currentBuild.result = "FAILURE"

    }

    finally {

        if (err) {

        throw err
        
        }
    }

}
