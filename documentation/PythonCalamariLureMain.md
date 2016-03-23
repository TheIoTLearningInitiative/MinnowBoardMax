Main
==

```python
#!/usr/bin/python

import argparse

if __name__ == '__main__':

    parser = argparse.ArgumentParser(description='MinnowBoard Max Workshop')
    parser.add_argument('-c', '--calamari', help='Calamari Mode')
    args = parser.parse_args()

    if args.calamari == 'rgb':

        from crgb import Crgb

        crgb = Crgb()
        crgb.start()

    if args.calamari == '7seg':

        from c7seg import C7seg

        c7seg = C7seg()
        c7seg.start()

    if args.calamari == 'pwm':

        from cpwm import Cpwm

        cpwm = Cpwm()
        cpwm.start()

    if args.calamari == 'buttons':

        from cbuttons import Cbuttons

        cbuttons = Cbuttons()
        cbuttons.start()

# End of File
```

