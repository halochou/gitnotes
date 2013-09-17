#Learning Perl Book Note
##C1.
##C2. Scalar
    use utf8;
    use warnings;

    single-quoted:'\\' '\''
    "hello" . "world" #helloworld
    "fred" x 3 #fredfredfred

    $name #variable
    print "the answer is",6*7,".\n"
    print "fred ${fred}s.\n"
    $omega = chr(0x03C9);
    $code_point = ord('×?');

    eq== ne!= lt< gt> le<= ge>=
    
    if($name gt 'fred'){
      print 'hello'
    } else {
      print 'world'
    }
    
    $count = 0;
    while ($count < 10) {
      $count += 2;
      print "count is now $count\n"; # Gives values 2 4 6 8 10
    }

    $line = <STDIN>;
    chomp($text);
    chomp($line = <STDIN>);

##C3 Lists & Arrays
    $fred[0] = "yabba";
    $fred[-1] == $fred[ $#fred ] #last element
    (1,2,3,4..100,"fred",4.5,$fred)  #list
    qw(alpha beta gamma) == ('alpha','beta','gamma') #quoted words
    ($a,$b,$c) = (1,2,3);

    @rocks = qw/ bedrock slate lava /;
    pop @rocks #lava poped
    shift @rocks #bedrock shifted
    push @rocks,"stone" #stone pushed right
    unshift @rocks,"stone" #stone unshifted left
    splice @array,start_point,len,"insert list"

    foreach $rock (qw/ bedrock slate lava /) {
      print "One rock is $rock.\n"; # Prints names of three rocks
    }
    foreach (qw/ bedrock slate lava /) {
      print;
    }

    use 5.012;
    @rocks = qw/ bedrock slate rubble granite /;
    while( my( $index, $value ) = each @rocks ) {
      say "$index: $value";
    }

    @people = qw( fred barney betty );
    @sorted = sort @people; #barney, betty, fred
    $number = 42 + @people; #42 + 3 = 45
    @reversed = reverse @people; # fred, betty, barney
    $reversed = reverse @people; # defryttebyenrab

    @lines = <STDIN>; #Read all lines till EOF
    chomp(@lines); #chomp all lines

##C4 Subroutines
    sub marine {
      $n += 1; # Global variable $n
      print "Hello, sailor number $n!\n";
      $n;
    }
    &marine; # says 1,2,3...

    $maximum = &max(3, 5, 10, 4, 6);
    sub max {
      my($max_so_far) = shift @_; # the first one is the largest yet seen
      foreach (@_) { # look at the remaining arguments
        if ($_ > $max_so_far) { # could this one be bigger yet?
          $max_so_far = $_;
        }
      }
      $max_so_far;
      return $_;
    }

    use 5.010;
    state $n = 0; #static variable

##C5 I/O
    chomp($line = <STDIN>);
