~~~~~~~~~~~~~~~~

//***FILE 036 IS A FIXPDS UTILITY FROM MR SAM GOLOB.  THIS CODE     *   FILE 036
//*           WAS WRITTEN BY MR ROBERT B. WEINSTEIN.  THIS          *   FILE 036
//*           UTILITY RESURRECTS DELETED MEMBERS OF A PDS, BUT IT   *   FILE 036
//*           DOES SO WITHOUT USING THE DIRECTORY.  THIS FILE IS    *   FILE 036
//*           IN IEBUPDTE SYSIN FORMAT.                             *   FILE 036
//*                                                                 *   FILE 036
//*           THIS PROGRAM STOWS NEW DIRECTORY ENTRIES FOR          *   FILE 036
//*           PHYSICAL FILES IN A DATASET WHICH WOULD LOOK LIKE A   *   FILE 036
//*           PDS MEMBER.  IT LOCATES THESE FILES WITHOUT BENEFIT   *   FILE 036
//*           OF A PREVIOUS GOOD DIRECTORY.  ALL IT NEEDS IS A      *   FILE 036
//*           BLANK DIRECTORY.                                      *   FILE 036
//*                                                                 *   FILE 036
//*           THIS FIXPDS PROGRAM RESTORES DELETED MEMBERS OF A     *   FILE 036
//*           PDS WITH A BACKWARD SEARCH, STARTING FROM THE END     *   FILE 036
//*           OF THE DATASET AND BROWSING EACH MEMBER (DELETED OR   *   FILE 036
//*           NOT) WITH ISPF BROWSE.  AFTER ENDING EACH BROWSE,     *   FILE 036
//*           YOU HAVE AN OPPORTUNITY TO STOW A NAME IN THE         *   FILE 036
//*           DIRECTORY FOR THAT MEMBER.  THE PROGRAM PROCEEDS      *   FILE 036
//*           BACKWARDS, MEMBER BY MEMBER, UNTIL YOU EXIT, OR       *   FILE 036
//*           UNTIL YOU REACH THE BEGINNING OF THE LIBRARY.         *   FILE 036
//*                                                                 *   FILE 036
//*           TWO FEATURES DISTINGUISH THIS PROGRAM FROM OTHERS     *   FILE 036
//*           OF THIS TYPE.  ONE, THE MEMBER SEARCH GOES            *   FILE 036
//*           BACKWARDS, STARTING FROM THE END OF THE DATASET AND   *   FILE 036
//*           GOING BACK, ONE MEMBER AT A TIME.  THIS ALLOWS YOU    *   FILE 036
//*           TO LOOK AT THE MOST RECENT ACTIVITY FIRST.  TWO,      *   FILE 036
//*           EACH MEMBER IS ISPF BROWSED.  IT CAN BE EXAMINED IN   *   FILE 036
//*           ITS ENTIRETY, AND IN DETAIL, BEFORE YOU DECIDE        *   FILE 036
//*           WHETHER TO STOW A DIRECTORY ENTRY FOR IT OR NOT.      *   FILE 036
//*                                                                 *   FILE 036
//*           IF YOU DO STOW A DIRECTORY ENTRY, IT DOESN'T MATTER   *   FILE 036
//*           IF ONE ALREADY EXISTS FOR THAT MEMBER.  THE NEW ONE   *   FILE 036
//*           IS CREATED ALSO.  IF AN OLD ENTRY WAS THERE TOO,      *   FILE 036
//*           UNDER A DIFFERENT NAME, AN "APPARENT ALIAS" IS        *   FILE 036
//*           CREATED.  USING THE "PDS" PROGRAM (IN CBT TAPE FILE   *   FILE 036
//*           182), ALL THE APPARENT ALIASES CREATED CAN BE FLAGGED *   FILE 036
//*           IN A JIFFY, USING THE "VERIFY" SUBCOMMAND OF PDS.     *   FILE 036
//*                                                                 *   FILE 036
//*           EDITOR'S NOTE.  IF ALL YOU WANT TO DO IS RESTORE      *   FILE 036
//*           DELETED MEMBERS OF A PDS, THE "PDS" PROGRAM ON FILE   *   FILE 036
//*           182 (WITH UTILITIES ON FILES 296 AND 112) IS          *   FILE 036
//*           PROBABLY BETTER THAN FIXPDS, AND PDS IS MUCH          *   FILE 036
//*           QUICKER.  A THIRD REFERENCE IS THE "PDSGAS" PROGRAM   *   FILE 036
//*           - FILE 316.  ALSO, THE "PDS" PROGRAM DOES MANY MORE   *   FILE 036
//*           THINGS, AND PDS IS NOT TOO HARD TO INSTALL.  I        *   FILE 036
//*           PERSONALLY HAVE RECEIVED MANY INQUIRIES FROM PEOPLE   *   FILE 036
//*           TRYING TO INSTALL FIXPDS, BECAUSE MY NAME IS ON THE   *   FILE 036
//*           CALL LIST.  I AM SPEAKING FROM MUCH EXPERIENCE.       *   FILE 036
//*           FIXPDS IS NICE TO HAVE, THOUGH, AND I DO NOT MEAN     *   FILE 036
//*           TO DISCOURAGE PEOPLE FROM INSTALLING IT.              *   FILE 036
//*           FIXPDS IS ESPECIALLY HELPFUL WHEN THE PDS DIRECTORY   *   FILE 036
//*           IS NOT RELIABLE.     SBG.                             *   FILE 036
//*                                                                 *   FILE 036
~~~~~~~~~~~~~~~~

