# Fractional part


Calculate the decimal representation of fractional number that is < 0 from a binary input in scheme.

ANSWER:

(define fract-part<br/>
&emsp;(lambda (f)<br/>
&emsp;&emsp;(if(= (string-length f) 0)<br/>
&emsp;&emsp;    0<br/>
&emsp;&emsp;    (+ (* (string->number (string (string-ref f (- (string-length f) 1)))) (expt 2 (- 0 (string-length f)))) (fract-part (substring f 0 (- (string-length f) 1) )))<br/>
&emsp;&emsp;    )<br/>
&emsp;&emsp;)<br/>
)<br/>


(fract-part "0"); → 0
(fract-part "01"); → 0.25
(fract-part "1"); → 0.5
(fract-part "101"); → 0.625
(fract-part "11"); → 0.75
(fract-part "0101"); → 0.3125