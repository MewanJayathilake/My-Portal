# My-Portal
code


<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
  <title>Dashbord | Life Saving Victoria - Public Portal</title>
  <link type="image/png" href="images/favicon.png" rel="icon" />

  <link rel="stylesheet" type="text/css" href="{{ asset('site/css/main.css')}}">
  <link rel="stylesheet" type="text/css" href="{{ asset('site/css/ui-styles.css')}}">
  <link rel="stylesheet" type="text/css" href="{{ asset('site/css/bulma.min.css')}}">
  <link rel="stylesheet" type="text/css" href="{{ asset('site/css/jquery.modal.min.css')}}">
  <link rel="stylesheet" type="text/css" href="{{ asset('site/css/bulma-steps.min.css')}}">
  <link rel="stylesheet" href="{{ asset('site/css/jquery-ui.css')}}">
  <!-- <link rel="stylesheet" href="css/jquery.dataTables.min.css"> -->

  <script src="{{ asset('site/js/jquery-3.4.1.js')}}"></script>
  <script src="{{ asset('site/js/jquery-ui.js')}}"></script>
  <script defer src="{{ asset('site/js/all.js')}}"></script>
  <script src="{{ asset('site/js/custom.js')}}"></script>
  <script src="{{ asset('site/js/jquery.modal.min.js')}}"></script>
  <script src="{{ asset('site/js/jquery.dataTables.min.js')}}"></script>
  
</head>
<body>
  <div class="login-page">
   <!--  <h1 class="title is-3 txt-primary-blue txt-center">WELCOME TO THE LSV TRAINING PORTAL</h1> -->
    <div class="login-container">
      <div class="inner">

        <ul class="logo-bar">
          <li class="brand-logo"><img src="{{ asset('site/images/logo.png')}}"></li>
          @foreach($social_icons as $social_icon)
          <li class="social-icon">
            <a href="{{$social_icon->url}}">
              <span class="{{$social_icon->class_one}}">
                <i class="{{$social_icon->class_two}}"></i>
              </span> 
            </a>
          </li>
          @endforeach
         
        </ul>

        <div class="login-form">
          <form action="{{url('dologin')}}" method="POST">
            @csrf
            @if( Session::get('message')!=NULL)
            <p class="txt-support-red"><?php echo Session::get('message'); ?></p>
            @endif
              @if (count($errors) > 0)
            
            <ul>
            @foreach ($errors->all() as $error)
            <li class="txt-support-red">{{ $error }}</li>
            @endforeach
            </ul>
            
            @endif
            <div class="field">
              <div class="control">
                <input class="input" type="text" placeholder="User Name" name="username">
              </div>
            </div>
            <div class="field">
              <div class="control">
                <input class="input" type="password" placeholder="Password" name="password">
              </div>
            </div>

            <div class="btn-container">
              <div class="columns  is-mobile">
                <div class="column is-half txt-left">
                  <a class="button delete-btn regular-btn">Reset</a>
                </div>
                <div class="column is-half txt-right">
                  <!-- <a class="button normal-btn regular-btn"></a> -->
                  <button class="button normal-btn regular-btn">Login</button>
                </div>
              </div>
              <div class="columns">
                <div class="column txt-center">
                  <a class="button normal-btn full-btn">Register</a>
                </div>
              </div>
            </div>

          </form>  
        </div>

      </div>
    </div>
  </div>
</body>
</html>
