first-one.pl
=========
# my first repository! just checking how this works!
use strict;

# Read some number of lines, concat them together (by a space), and print them.
# Stops when it reaches the indicated count, the end of file, or the line STOP!

print "How many lines? ";
my $num = <STDIN>;
$num > 0 or die "Num must be positive.  You entered $num";

my $accum = "";
my $sep = "";
while(my $line = <STDIN>) {
    chomp $line;
    if($line eq "STOP!") { last; }
    $accum = "$accum$sep$line";
    if(--$num == 0) { last; }
    $sep = " ";
}

print "$accum\n";