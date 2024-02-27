# utl-reading-and-resolving-sas-variable-definitions-in-your-input-data
Reading and resolving sas variable definitions in your input data 
    %let pgm=utl-reading-and-resolving-sas-variable-definitions-in-your-input-data;

    Reading and resolving sas variable definitions in your input data

    github
    http://tinyurl.com/muxnbdrv
    https://github.com/rogerjdeangelis/utl-reading-and-resolving-sas-variable-definitions-in-your-input-data


    /**************************************************************************************************************************/
    /*                                                          |                                                             */
    /*                                                          |                                                             */
    /*             INPUT PROCESS                                |                       OUTPUT                                */
    /*                                                          |                                                             */
    /*  data want;                                              |    X1          X2         X3         X4         X5          */
    /*     input (x1-x5) (= $20.);                              |                                                             */
    /*  cards4;                                                 | checking    duration    history    purpose    amount        */
    /*  x1=checking x2=duration x3=history x4=purpose x5=amount | checking    duration    history    purpose    amount        */
    /*  x1=checking x2=duration x3=history x4=purpose x5=amount |                                                             */
    /*                                                          |                                                             */
    /**************************************************************************************************************************/


    data want ;
       input (x1-x5) (= $20.);
    cards4;
    x1=checking x2=duration x3=history x4=purpose x5=amount
    x1=checking x2=duration x3=history x4=purpose x5=amount
    ;;;;
    run;quit;

    proc print;
    run;quit;

    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /*  WANT total obs=2 27MAY2022:11:45:52                                                                                   */
    /*                                                                                                                        */
    /*  Obs       X1          X2         X3         X4         X5                                                             */
    /*                                                                                                                        */
    /*   1     checking    duration    history    purpose    amount                                                           */
    /*   2     checking    duration    history    purpose    amount                                                           */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
