Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, a Playstation2 emulator, and many reverse engineering tools like IDA Pro, Ghidra, and PS2DIS.

The difference between physical and logical addresses is 0xFFF80

<pre>
Physical Address(es):       Logical Address(es):        Description: 
0x0011A010 - 0x0011A090     0x00219F90 - 0x0021A010     Function: 
                                                        signed int is_oni_course_passed(signed int course, signed int style)
0x0011A090 - 0x0011A128     0x0021A010 - 0x0021A0A8     Function: 
                                                        signed int onimode_get_course_nm_color(signed int id)
0x0011A130 - 0x0011A4AC     0x0021A0B0 - 0x0021A42C     Function: 
                                                        signed int onimode_get_additional_life(signed int id, signed int stage, signed int is_single)
0x0011A4B0 - 0x0011A4D0     0x0021A430 - 0x0021A450     Function: 
                                                        oni_course* onimode_get_course_list(signed int id)
0x0011A4D0 - 0x0011A79C     0x0021A450 - 0x0021A71C     Function: 
                                                        void onimode_set_order_mode(signed int id, signed int stage_num)
0x0011A7A0 - 0x0011A9F4     0x0021A720 - 0x0021A974     Function: 
                                                        void onimode_get_order_mode(signed int id, signed int stage_num)
0x0011AA00 - 0x0011AA30     0x0021A980 - 0x0021A9B0     Function: 
                                                        signed int onimode_is_course_order(signed int id)
0x0011AA30 - 0x0011AA3C     0x0021A9B0 - 0x0021A9BC     Function: 
                                                        signed int onimode_is_course_random(signed int id)
0x0011AA40 - 0x0011AC44     0x0021A9C0 - 0x0021ABC4     Function: 
                                                        void onimode_order_setup()
0x0011AC50 - 0x0011B858     0x0021ABD0 - 0x0021B7D8     Function: 
                                                        void onimode_random_setup()

0x0011C7E0 - 0x0011CB7C     0x0021C760 - 0x0021CAFC     Function: 
                                                        void* sp_ending_get_bk_movie_prim(signed int n)
0x0011CB80 - 0x0011D380     0x0021CB00 - 0x0021D300     Function: 
                                                        signed int special_ending_disp_step(void* w)
0x0011D380 - 0x0011D440     0x0021D300 - 0x0021D3C0     Function: 
                                                        void special_ending_disp_init(void* w)

0x00120AB0 - 0x00120CB8     0x00220A30 - 0x00220C38     Function:
                                                        void EdsSelectPrintDigit(signed int _x, signed int _y, unsigned int _dig00, unsigned int _dig01, char _figure, unsigned char _alpha)
0x00120CC0 - 0x00122044     0x00220C40 - 0x00221FC4     Function:
                                                        void EdsOrderCommon(_EDSSYS_W * _eds)
0x00122050 - 0x001223B0     0x00221FD0 - 0x00222330     Function:
                                                        void EdsOrderInit(_EDSSYS_W * _eds)
0x001223B0 - 0x001223C0     0x00222330 - 0x00222340     Function:
                                                        void EdsToOrderTexInit(_EDSSYS_W * _eds)
0x001223C0 - 0x001224B8     0x00222340 - 0x00222438     Function:
                                                        void EdsPlayCommon(_EDSSYS_W * _eds)
0x001224C0 - 0x00122EA0     0x00222440 - 0x00222E20     Function:
                                                        void EdsPlayInit(_EDSSYS_W * _eds)
0x00122EA0 - 0x00122EE8     0x00222E20 - 0x00222E68     Function:
                                                        void EdsMenuBlackWait(_EDSSYS_W * _eds)
0x00122EF0 - 0x00123E14     0x00222E70 - 0x00223D94     Function:
                                                        void EdsMenuCommon(_EDSSYS_W * _eds)
0x00123E20 - 0x001241B8     0x00223DA0 - 0x00224138     Function:
                                                        void EdsMenuInit2(_EDSSYS_W * _eds)
0x001241C0 - 0x0012459C     0x00224140 - 0x0022451C     Function:
                                                        void EdsMenuInit(_EDSSYS_W * _eds)
0x001245A0 - 0x001246E8     0x00224520 - 0x00224668     Function:
                                                        void EdsToMenuTexInit(_EDSSYS_W * _eds)
0x001246F0 - 0x00124820     0x00224670 - 0x002247A0     Function:
                                                        void EdsWarningCommon(_EDSSYS_W * _eds)
0x00124820 - 0x0012487C     0x002247A0 - 0x002247FC     Function:
                                                        void EdsWarningInit(_EDSSYS_W * _eds)
0x00124880 - 0x001248E0     0x00224800 - 0x00224860     Function:
                                                        void EdsMainMenuTexture(_EDSSYS_W * _eds)
0x001248E0 - 0x00124914     0x00224860 - 0x00224894     Function:
                                                        void EdsMainMenuInit(_EDSSYS_W * _eds)
0x00124920 - 0x00124A94     0x002248A0 - 0x00224A14     Function:
                                                        signed int EdsSelectMain(_EDSSYS_W * _eds)
0x00124AA0 - 0x00124BC8     0x00224A20 - 0x00224B48     Function:
                                                        signed int EdsInitBreakTex(_EDSSYS_W * _eds)
0x00124BD0 - 0x00124E50     0x00224B50 - 0x00224DD0     Function:
                                                        signed int EdsInitTex(_EDSSYS_W * _eds, signed int _num)
0x00124E50 - 0x00124E5C     0x00224DD0 - 0x00224DDC     Function:
                                                        void EdsSystemEnd()
0x00124E60 - 0x00124E9C     0x00224DE0 - 0x00224E1C     Function:
                                                        signed int EdsSystemMain()
0x00124EA0 - 0x00124F5C     0x00224E20 - 0x00224EDC     Function:
                                                        void EdsSystemInit(_GAME_MODE_W * game_mode_w)
0x00124F60 - 0x00124F68     0x00224EE0 - 0x00224EE8     Function:
                                                        void EdsSetPreRead()
0x00124F70 - 0x00125158     0x00224EF0 - 0x002250D8     Function:
                                                        signed int Update_Optscr()
0x00125160 - 0x001257F8     0x002250E0 - 0x00225778     Function:
                                                        signed int View_Optscr()
0x00125800 - 0x00125DA8     0x00225780 - 0x00225D28     Function:
                                                        signed int Control_Optscr()
0x00125DB0 - 0x00125E68     0x00225D30 - 0x00225DE8     Function:
                                                        signed int Init_Optscr()
0x00125E70 - 0x00125EE0     0x00225DF0 - 0x00225E60     Function:
                                                        void set_no_space_msg_cmes_j(unsigned char * str, signed int flag)
0x00125EE0 - 0x00125F6C     0x00225E60 - 0x00225EEC     Function:
                                                        void EdsWinSelectAllFrameDisp(unsigned char _alpha)
0x00125F70 - 0x001261F0     0x00225EF0 - 0x00226170     Function:
                                                        void EdsWinSelectFrame(signed int _x, signed int _y, unsigned char _alpha, signed int _flag)
0x001261F0 - 0x001262B4     0x00226170 - 0x00226234     Function:
                                                        void EdsWinSelectBox(signed int _x, signed int _y, char _flag)
0x001262C0 - 0x00126498     0x00226240 - 0x00226418     Function:
                                                        void EdsCheck(signed int _x, signed int _y, signed int _type, unsigned char _alpha)
0x001264A0 - 0x00126648     0x00226420 - 0x002265C8     Function:
                                                        void EdsWinAllDestroy()
0x00126650 - 0x00126690     0x002265D0 - 0x00226610     Function:
                                                        void EdsWinSetTex(_EDSWIN_W * winw, unsigned char _tex)
0x00126690 - 0x00126710     0x00226610 - 0x00226690     Function:
                                                        void EdsWinSetMoveXY(_EDSWIN_W * winw, float x, float y)
0x00126710 - 0x00126768     0x00226690 - 0x002266E8     Function:
                                                        void EdsWinSetXY(_EDSWIN_W * winw, float x, float y)
0x00126770 - 0x001267D4     0x002266F0 - 0x00226754     Function:
                                                        void EdsWinSetType(_EDSWIN_W * winw, char type)
0x001267E0 - 0x001268FC     0x00226760 - 0x0022687C     Function:
                                                        void EdsWinSetMode(_EDSWIN_W * winw, signed int mode)
0x00126900 - 0x001269E0     0x00226880 - 0x00226960     Function:
                                                        void EdsWinSetDefaultPartsWH(_EDSWIN_W * winw)
0x001269E0 - 0x00126AB8     0x00226960 - 0x00226A38     Function:
                                                        void EdsWinDefaultAllSet(_EDSWIN_W * winw)
0x00126AC0 - 0x00126D58     0x00226A40 - 0x00226CD8     Function:
                                                        signed int EdsWinAlphaAnime(_EDSWIN_W * winw)
0x00126D60 - 0x00126F28     0x00226CE0 - 0x00226EA8     Function:
                                                        signed int EdsWinWHMove(_EDSWIN_W * winw)
0x00126F30 - 0x00127140     0x00226EB0 - 0x002270C0     Function:
                                                        signed int EdsWinXYMove(_EDSWIN_W * winw, signed int speed)
0x00127140 - 0x001273E0     0x002270C0 - 0x00227360     Function:
                                                        signed int EdsWinXYWHMove(_EDSWIN_W * winw, signed int speed)
0x001273E0 - 0x00127BF8     0x00227360 - 0x00227B78     Function:
                                                        void EdsWinDisp(_EDSWIN_W * winw)
0x00127C00 - 0x00127C60     0x00227B80 - 0x00227BE0     Function:
                                                        signed int EdsWinDestroy(_EDSWIN_W * winw)
0x00127C60 - 0x00127E40     0x00227BE0 - 0x00227DC0     Function:
                                                        signed int EdsWinClose(_EDSWIN_W * winw)
0x00127E40 - 0x00127F08     0x00227DC0 - 0x00227E88     Function:
                                                        signed int EdsWinMain(_EDSWIN_W * winw)
0x00127F10 - 0x00128178     0x00227E90 - 0x002280F8     Function:
                                                        signed int EdsWinOpen(_EDSWIN_W * winw)
0x00128180 - 0x0012818C     0x00228100 - 0x0022810C     Function:
                                                        signed int EdsWinSet(_EDSWIN_W * winw)
0x00128190 - 0x00128274     0x00228110 - 0x002281F4     Function:
                                                        _EDSWIN_W * EdsWinGetInit(signed int id)
0x00128280 - 0x00128340     0x00228200 - 0x002282C0     Function:
                                                        void EdsWinFunc(_EDSWIN_W * winw)
0x00128340 - 0x001284F0     0x002282C0 - 0x00228470     Function:
                                                        void EdsAidPrintFont(signed int _x, signed int _y, char * _str, signed int _color, unsigned char _alpha, signed int texid)
0x001284F0 - 0x001286FC     0x00228470 - 0x0022867C     Function:
                                                        void EdsScoreCreate(signed int _value)
0x00128700 - 0x001289B4     0x00228680 - 0x00228934     Function:
                                                        void EdsNextStageCreate()
0x001289C0 - 0x00128A60     0x00228940 - 0x002289E0     Function:
                                                        void EdsBeforeStageDataSet()
0x00128A60 - 0x00128B00     0x002289E0 - 0x00228A80     Function:
                                                        signed int EdsMOMax()
0x00128B00 - 0x00128EB0     0x00228A80 - 0x00228E30     Function:
                                                        signed int EdsPlayFlag(signed int _music, signed int _mode, signed int _bit)
0x00128EB0 - 0x00128F80     0x00228E30 - 0x00228F00     Function:
                                                        music_info * EdsGetMipTable(signed int _num)
0x00128F80 - 0x00129118     0x00228F00 - 0x00229098     Function:
                                                        void EdsInitMipTable(_EDSSYS_W * _eds)
0x00129120 - 0x00129488     0x002290A0 - 0x00229408     Function:
                                                        signed int EdsGetLevelType(_EDSSYS_W * _eds, signed int num)
0x00129490 - 0x00129740     0x00229410 - 0x002296C0     Function:
                                                        void EdsInitOrderFlag()
0x00129740 - 0x00129B0C     0x002296C0 - 0x00229A8C     Function:
                                                        void EdsTrackSorting(signed int _flag)
0x00129B10 - 0x00129BE0     0x00229A90 - 0x00229B60     Function:
                                                        void EdsInitAllMusicMax(signed int flag)
0x00129BE0 - 0x00129C34     0x00229B60 - 0x00229BB4     Function:
                                                        void EdsBreakStageEnd(_EDSSYS_W * _eds)
0x00129C40 - 0x00129E20     0x00229BC0 - 0x00229DA0     Function:
                                                        void EdsBreakStageMain(_EDSSYS_W * _eds)
0x00129E20 - 0x00129F20     0x00229DA0 - 0x00229EA0     Function:
                                                        void EdsBreakStageInit(_EDSSYS_W * _eds)
0x00129F20 - 0x0012A130     0x00229EA0 - 0x0022A0B0     Function:
                                                        void EdsRecordPrintDigit(signed int _x, signed int _y, unsigned int _dig00, unsigned int _dig01, char _figure, unsigned char _alpha)
0x0012A130 - 0x0012A528     0x0022A0B0 - 0x0022A4A8     Function:
                                                        signed int EdsRenewalRecord(_EDSSYS_W * _eds, signed int flag)
0x0012A530 - 0x0012A568     0x0022A4B0 - 0x0022A4E8     Function:
                                                        void EdsRecordEnd(_EDSSYS_W * _eds)
0x0012A570 - 0x0012B010     0x0022A4F0 - 0x0022AF90     Function:
                                                        void EdsRecordCommon(_EDSSYS_W * _eds)
0x0012B010 - 0x0012B57C     0x0022AF90 - 0x0022B4FC     Function:
                                                        void EdsRecordTexture(_EDSSYS_W * _eds)
                                                        
0x0012D790 - 0x0012D7A4     0x0022D710 - 0x0022D724     Function (from SYSCLIB - system C library):
                                                        int abs(int number)
0x0012D808 - 0x0012D840     0x0022D788 - 0x0022D7C0     Function (from SYSCLIB - system C library):
                                                        void bzero(void* dst, size_t n);
                                                        
0x00138EC0 - 0x00138EE8     0x00238E40 - 0x00238E68     Function:
                                                        unsigned char* mesGetCancel(signed int id0)
0x00138EF0 - 0x00138F18     0x00238E70 - 0x00238E98     Function:	
                                                        unsigned char* mesGetOk(signed int id0)
0x00138F20 - 0x00138F64     0x00238EA0 - 0x00238EE4     Function:	
                                                        unsigned char* mesGetLanguage01(signed int id0, signed int id1)
                                                        

                                                        
             0x00156440                  0x002563C0     Returning DanceDanceRevolution Song Grouping - Red Channel Value
             0x00156444                  0x002563C4     Returning DanceDanceRevolution Song Grouping - Red Channel Value
             0x00156448                  0x002563C8     Returning DanceDanceRevolution Song Grouping - Red Channel Value
             0x0015644C                  0x002563CC     Returning DanceDanceRevolution Song Grouping - Green Channel Value
             0x00156450                  0x002563D0     Returning DanceDanceRevolution Song Grouping - Green Channel Value
             0x00156454                  0x002563D4     Returning DanceDanceRevolution Song Grouping - Green Channel Value
             0x00156458                  0x002563D8     Returning DanceDanceRevolution Song Grouping - Blue Channel Value
             0x0015645C                  0x002563DC     Returning DanceDanceRevolution Song Grouping - Blue Channel Value
             0x00156460                  0x002563E0     Returning DanceDanceRevolution Song Grouping - Blue Channel Value
             0x00156464                  0x002563E4     MAX2 Licenses & Konami Originals Song Grouping - Red Channel Value
             0x00156468                  0x002563E8     MAX2 Licenses & Konami Originals Song Grouping - Red Channel Value
             0x0015646C                  0x002563EC     MAX2 Licenses & Konami Originals Song Grouping - Red Channel Value
             0x00156470                  0x002563F0     MAX2 Licenses & Konami Originals Song Grouping - Green Channel Value
             0x00156474                  0x002563F4     MAX2 Licenses & Konami Originals Song Grouping - Green Channel Value
             0x00156478                  0x002563F8     MAX2 Licenses & Konami Originals Song Grouping - Green Channel Value
             0x0015647C                  0x002563FC     MAX2 Licenses & Konami Originals Song Grouping - Blue Channel Value
             0x00156480                  0x00256400     MAX2 Licenses & Konami Originals Song Grouping - Blue Channel Value
             0x00156484                  0x00256404     MAX2 Licenses & Konami Originals Song Grouping - Blue Channel Value
             0x001564AC                  0x0025642C     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Red Channel Value
             0x001564B0                  0x00256430     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Red Channel Value
             0x001564B4                  0x00256434     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Red Channel Value
             0x001564B8                  0x00256438     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Green Channel Value
             0x001564BC                  0x0025643C     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Green Channel Value
             0x001564C0                  0x00256440     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Green Channel Value
             0x001564C4                  0x00256444     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Blue Channel Value
             0x001564C8                  0x00256448     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Blue Channel Value
             0x001564CC                  0x0025644C     ORDER 1/ORDER 2/ORDER 3 Nonstop Challenge Course Choices - Blue Channel Value
             0x001564F4                  0x00256474     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Red Channel Value
             0x001564F8                  0x00256478     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Red Channel Value
             0x001564FC                  0x0025647C     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Red Channel Value
             0x00156500                  0x00256480     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Green Channel Value
             0x00156504                  0x00256484     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Green Channel Value
             0x00156508                  0x00256488     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Green Channel Value
             0x0015650C                  0x0025648C     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Blue Channel Value
             0x00156510                  0x00256490     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Blue Channel Value
             0x00156514                  0x00256494     GHOST ROAD/ONI ROAD Nonstop Challenge Course Choices - Blue Channel Value
             0x00156518                  0x00256498     ULTRA 12 Nonstop Challenge Course Choice - Red Channel Value
             0x0015651C                  0x0025649C     ULTRA 12 Nonstop Challenge Course Choice - Red Channel Value
             0x00156520                  0x002564A0     ULTRA 12 Nonstop Challenge Course Choice - Red Channel Value
             0x00156524                  0x002564A4     ULTRA 12 Nonstop Challenge Course Choice - Green Channel Value
             0x00156528                  0x002564A8     ULTRA 12 Nonstop Challenge Course Choice - Green Channel Value
             0x0015652C                  0x002564AC     ULTRA 12 Nonstop Challenge Course Choice - Green Channel Value
             0x00156530                  0x002564B0     ULTRA 12 Nonstop Challenge Course Choice - Blue Channel Value
             0x00156534                  0x002564B4     ULTRA 12 Nonstop Challenge Course Choice - Blue Channel Value
             0x00156538                  0x002564B8     ULTRA 12 Nonstop Challenge Course Choice - Blue Channel Value
             0x00156584                  0x00256504     Nonstop Course Song Text Color Mask - Light Difficulty - Red Channel Value
             0x00156588                  0x00256508     Nonstop Course Song Text Color Mask - Light Difficulty - Red Channel Value
             0x0015658C                  0x0025650C     Nonstop Course Song Text Color Mask - Light Difficulty - Red Channel Value
             0x00156590                  0x00256510     Nonstop Course Song Text Color Mask - Light Difficulty - Green Channel Value
             0x00156594                  0x00256514     Nonstop Course Song Text Color Mask - Light Difficulty - Green Channel Value
             0x00156598                  0x00256518     Nonstop Course Song Text Color Mask - Light Difficulty - Green Channel Value
             0x0015659C                  0x0025651C     Nonstop Course Song Text Color Mask - Light Difficulty - Blue Channel Value
             0x001565A0                  0x00256520     Nonstop Course Song Text Color Mask - Light Difficulty - Blue Channel Value
             0x001565A4                  0x00256524     Nonstop Course Song Text Color Mask - Light Difficulty - Blue Channel Value
             0x001565A8                  0x00256528     Nonstop Course Song Text Color Mask - Standard Difficulty - Red Channel Value
             0x001565AC                  0x0025652C     Nonstop Course Song Text Color Mask - Standard Difficulty - Red Channel Value
             0x001565B0                  0x00256530     Nonstop Course Song Text Color Mask - Standard Difficulty - Red Channel Value
             0x001565B4                  0x00256534     Nonstop Course Song Text Color Mask - Standard Difficulty - Green Channel Value
             0x001565B8                  0x00256538     Nonstop Course Song Text Color Mask - Standard Difficulty - Green Channel Value
             0x001565BC                  0x0025653C     Nonstop Course Song Text Color Mask - Standard Difficulty - Green Channel Value
             0x001565C0                  0x00256540     Nonstop Course Song Text Color Mask - Standard Difficulty - Blue Channel Value
             0x001565C4                  0x00256544     Nonstop Course Song Text Color Mask - Standard Difficulty - Blue Channel Value
             0x001565C8                  0x00256548     Nonstop Course Song Text Color Mask - Standard Difficulty - Blue Channel Value
             0x001565CC                  0x0025654C     Nonstop Course Song Text Color Mask - Heavy Difficulty - Red Channel Value
             0x001565D0                  0x00256550     Nonstop Course Song Text Color Mask - Heavy Difficulty - Red Channel Value
             0x001565D4                  0x00256554     Nonstop Course Song Text Color Mask - Heavy Difficulty - Red Channel Value
             0x001565D8                  0x00256558     Nonstop Course Song Text Color Mask - Heavy Difficulty - Green Channel Value
             0x001565DC                  0x0025655C     Nonstop Course Song Text Color Mask - Heavy Difficulty - Green Channel Value
             0x001565E0                  0x00256560     Nonstop Course Song Text Color Mask - Heavy Difficulty - Green Channel Value
             0x001565E4                  0x00256564     Nonstop Course Song Text Color Mask - Heavy Difficulty - Blue Channel Value
             0x001565E8                  0x00256568     Nonstop Course Song Text Color Mask - Heavy Difficulty - Blue Channel Value
             0x001565EC                  0x0025656C     Nonstop Course Song Text Color Mask - Heavy Difficulty - Blue Channel Value
             0x001565F0                  0x00256570     Nonstop Course Song Text Color Mask - Challenge Difficulty - Red Channel Value
             0x001565F4                  0x00256574     Nonstop Course Song Text Color Mask - Challenge Difficulty - Red Channel Value
             0x001565F8                  0x00256578     Nonstop Course Song Text Color Mask - Challenge Difficulty - Red Channel Value
             0x001565FC                  0x0025657C     Nonstop Course Song Text Color Mask - Challenge Difficulty - Green Channel Value
             0x00156600                  0x00256580     Nonstop Course Song Text Color Mask - Challenge Difficulty - Green Channel Value
             0x00156604                  0x00256584     Nonstop Course Song Text Color Mask - Challenge Difficulty - Green Channel Value
             0x00156608                  0x00256588     Nonstop Course Song Text Color Mask - Challenge Difficulty - Blue Channel Value
             0x0015660C                  0x0025658C     Nonstop Course Song Text Color Mask - Challenge Difficulty - Blue Channel Value
             0x00156610                  0x00256590     Nonstop Course Song Text Color Mask - Challenge Difficulty - Blue Channel Value 
0x001566E0 - 0x0015670C     0x00256660 - 0x0025668C     Foot Rating Foot Color RGB Values - Music Select Screen
             0x001566E0                  0x00256660     Light Difficulty Foot Color - Red Channel Value
             0x001566E4                  0x00256664     Light Difficulty Foot Color - Green Channel Value
             0x001566E8                  0x00256668     Light Difficulty Foot Color - Blue Channel Value
             0x001566EC                  0x0025666C     Standard Difficulty Foot Color - Red Channel Value
             0x001566F0                  0x00256670     Standard Difficulty Foot Color - Green Channel Value
             0x001566F4                  0x00256674     Standard Difficulty Foot Color - Blue Channel Value
             0x001566F8                  0x00256678     Heavy Difficulty Foot Color - Red Channel Value
             0x001566FC                  0x0025667C     Heavy Difficulty Foot Color - Green Channel Value
             0x00156700                  0x00256680     Heavy Difficulty Foot Color - Blue Channel Value
             0x00156704                  0x00256684     Challenge Difficulty Foot Color - Red Channel Value
             0x00156708                  0x00256688     Challenge Difficulty Foot Color - Green Channel Value
             0x0015670C                  0x0025668C     Challenge Difficulty Foot Color - Blue Channel Value
0x00156BA0 - 0x00156BBC     0x00256B20 - 0x00256B3C     Difficulty Choice Box Positions (Difficulty Selection Screen)
             0x00156BA0                  0x00256B20     Light Difficulty - X Pos
             0x00156BA4                  0x00256B24     Light Difficulty - Y Pos
             0x00156BA8                  0x00256B28     Standard Difficulty - X Pos
             0x00156BAC                  0x00256B2C     Standard Difficulty - Y Pos
             0x00156BB0                  0x00256B30     Heavy Difficulty - X Pos
             0x00156BB4                  0x00256B34     Heavy Difficulty - Y Pos    
             0x00156BB8                  0x00256B38     Challenge Difficulty - X Pos
             0x00156BBC                  0x00256B3C     Challenge Difficulty - Y Pos                     
0x001566B0 - 0x001566D4     0x00256630 - 0x00256654     Groove Radar Label Positions
             0x001566B0                  0x00256630     Groove Radar Label - Stream - X Position
             0x001566B4                  0x00256634     Groove Radar Label - Stream - Y Position
             0x001566B8                  0x00256638     Groove Radar Label - Voltage - X Position
             0x001566BC                  0x0025663C     Groove Radar Label - Voltage - Y Position
             0x001566C0                  0x00256640     Groove Radar Label - Air - X Position
             0x001566C4                  0x00256644     Groove Radar Label - Air - Y Position
             0x001566C8                  0x00256648     Groove Radar Label - Freeze - X Position
             0x001566CC                  0x0025664C     Groove Radar Label - Freeze - Y Position
             0x001566D0                  0x002566D0     Groove Radar Label - Chaos - X Position
             0x001566D4                  0x002566D4     Groove Radar Label - Chaos - Y Position   
0x00156D60 - 0x00156D7C     0x00256CE0 - 0x00256CFC     Difficulty Selection Cursor Positions (Difficulty Selection Screen)
             0x00156D60                  0x00256CE0     Light Mode - X Position
             0x00156D64                  0x00256CE4     Light Mode - Y Position
             0x00156D68                  0x00256CE8     Standard Mode - X Position
             0x00156D6C                  0x00256CEC     Standard Mode - Y Position
             0x00156D70                  0x00256CF0     Heavy Mode - X Position
             0x00156D74                  0x00256CF4     Heavy Mode - Y Position
             0x00156D78                  0x00256CF8     Nonstop Challenge - X Position
             0x00156D7C                  0x00256CFC     Nonstop Challenge - Y Position
0x00157600 - 0x0015760C     0x00257580 - 0x0025758C     Main Menu Graphics Indexes
             0x00157600                  0x00257580     Index For Main Menu Option Text Graphic
             0x00157604                  0x00257584     Index For Main Menu Background Graphic
             0x00157608                  0x00257588     Index For Main Menu "NEW!" Icon Graphic
             0x0015760C                  0x0025758C     Index For Main Menu Information Footer Graphic
0x00157610 - 0x0015763C     0x00257590 - 0x002575BC     Main Menu Choice Graphic Y Offsets
             0x00157610                  0x00257590     Unused / Empty
             0x00157614                  0x00257594     "Game Mode" Main Menu Choice Graphic Y Offset
             0x00157618                  0x00257598     "Diet Mode  Main Menu Choice Graphic Y Offset
             0x0015761C                  0x0025759C     "Training Mode" Main Menu Choice Graphic Y Offset
             0x00157620                  0x002575A0     "Edit Mode" Main Menu Choice Graphic Y Offset
             0x00157622                  0x002575A4     "Options" Main Menu Choice Graphic Y Offset
             0x00157624                  0x002575A8     "Records" Main Menu Choice Graphic Y Offset
             0x00157628                  0x002575AC     "Information" Main Menu Choice Graphic Y Offset
             0x0015762C                  0x002575BO     "Endless Mode" Main Menu Choice Graphic Y Offset
             0x00157630                  0x002575B4     Unused / Empty        
             0x00157632                  0x002575B8     Unused / Empty        
             0x00157634                  0x002575BC     Unused / Empty                            
0x00160AC0 - 0x00163540     0x00260A40 - 0x002634C0     Song music_info Structures
             0x00160AC0                  0x00260A40     music_info structure For Long Train Runnin'
             0x00160B48                  0x00260AC8     music_info structure For Maximum Overdrive
             0x00160BD0                  0x00260B50     music_info structure For Waka Laka
             0x00160C58                  0x00260BD8     music_info structure For Baby Love Me
             0x00160CE0                  0x00260C60     music_info structure For D2R
             0x00160D68                  0x00260CE8     music_info structure For Destiny
             0x00160DF0                  0x00260D70     music_info structure For Living In America
             0x00160E78                  0x00260DF8     music_info structure For Sweet Sweet ♥ Magic
             0x00160F00                  0x00260E80     music_info structure For Ever Snow
             0x00160E88                  0x00260E08     music_info structure For AM-3P (303 BASS MIX)
             0x00161010                  0x00260F90     music_info structure For The Reflex
             0x00161098                  0x00261018     music_info structure For So Fabulous So Fierce (Freak Out!)
             0x00161120                  0x002610A0     music_info structure For Drifting Away
             0x001611A8                  0x00261128     music_info structure For Stay
             0x00161230                  0x002611B0     music_info structure For Secret Rendez-vous
             0x001612B8                  0x00261238     music_info structure For Little Boy (Boy Oh Boy Mix)
             0x00161340                  0x002612C0     music_info structure For Rain of Sorrow
             0x001613C8                  0x00261348     music_info structure For Maxx Unlimited
             0x00161450                  0x002613D0     music_info structure For Dive To The Night
             0x001614D8                  0x00261458     music_info structure For Tsugaru
             0x00161560                  0x002614E0     music_info structure For BRE∀K DOWN!
             0x001615E8                  0x00261568     music_info structure For Burning Heat! (3 Option Mix)
             0x00161670                  0x002615F0     music_info structure For Nothing Gonna Stop
             0x001616F8                  0x00261678     music_info structure For Fantasy
             0x00161780                  0x00261700     music_info structure For i feel ...
             0x00161808                  0x00261788     music_info structure For CANDY ♥ 
             0x00161890                  0x00261810     music_info structure For Spin the Disc
             0x00161918                  0x00261898     music_info structure For Trance De Janeiro
             0x001619A0                  0x00261920     music_info structure For Look At Us
             0x00161A28                  0x002619A8     music_info structure For The Whistle Song (Blow My Whistle Bitch)
             0x00161AB0                  0x00261A30     music_info structure For 革命 (Kakumei)
             0x00161B38                  0x00261AB8     music_info structure For AFRONOVA (From Nonstop Megamix)
             0x00161BC0                  0x00261B40     music_info structure For AM-3P (AM EAST MIX)
             0x00161C48                  0x00261BC8     music_info structure For Brillant 2U (K.O.G G3 Mix)
             0x00161CD0                  0x00261C50     music_info structure For B4U (B4 ZA BEAT MIX)
             0x00161D58                  0x00261CD8     music_info structure For DROP OUT (From Nonstop Megamix)
             0x00161DE0                  0x00261D60     music_info structure For Dynamite Rave (B4 ZA BEAT MIX)
             0x00161E68                  0x00261DE8     music_info structure For Hysteria 2001
             0x00161EF0                  0x00261E70     music_info structure For 祭 JAPAN (From Nonstop Megamix)
             0x00161F78                  0x00261EF8     music_info structure For SEXY PLANET (From Nonstop Megamix)
             0x00162000                  0x00261F80     music_info structure For Super Star (From Nonstop Megamix)
             0x00162088                  0x00262008     music_info structure For Still In My Heart (MOMO MIX)
             0x00162110                  0x00262090     music_info structure For Wild Rush (From Nonstop Megamix)
             0x00162198                  0x00262118     music_info structure For Burnin' The Floor (BLUE Fire mix)
             0x00162220                  0x002621A0     music_info structure For Tsugaru (Apple Mix)
             0x001622A8                  0x00262228     music_info structure For Ecstacy (Mifnight Blue Mix)
             0x00162330                  0x002622B0     music_info structure For Silent Hill (3rd Christmas Mix)
             0x001623B8                  0x00262338     music_info structure For Celebrate Nite (Euro Trance Style)
             0x00162440                  0x002623C0     music_info structure For Higher (Next Morning Mix)
             0x001624C8                  0x00262448     music_info structure For My Summer Love (Tommy's Smile Mix)
             0x00162550                  0x002624D0     music_info structure For Look to the Sky (True Color Mix)
             0x001625D8                  0x00262558     music_info structure For Cutie Chaser (Morning Mix)
             0x00162660                  0x002625E0     music_info structure For Do It Right (Harmonized 25step Mix)
             0x001626E8                  0x00262668     music_info structure For Drop the Bomb -System S.F Mix-
             0x00162770                  0x002626F0     music_info structure For Dynamite Rave (Down Bird SOTA Mix)
             0x001627F8                  0x00262778     music_info structure For I'm For Real
             0x00162880                  0x00262800     music_info structure For Jam & Marmalade
             0x00162908                  0x00262888     music_info structure For Kind Lady
             0x00162990                  0x00262910     music_info structure For Logical Dash
             0x00162A18                  0x00262998     music_info structure For Overblast!!
             0x00162AA0                  0x00262A20     music_info structure For Peace-Out
             0x00162B28                  0x00262AA8     music_info structure For So In Love
             0x00162BB0                  0x00262B30     music_info structure For The Shining Polaris
             0x00162C38                  0x00262BB8     music_info structure For Look To The Sky (Trance Mix)
             0x00162CC0                  0x00262C40     music_info structure For Do It Right (80s Electro Mix)
             0x00162D48                  0x00262CC8     music_info structure For Kind Lady (Interlude)
             0x00162DD0                  0x00262D50     music_info structure For B4U
             0x00162E58                  0x00262DD8     music_info structure For Crash!
             0x00162EE0                  0x00262E60     music_info structure For Dead End
             0x00162F68                  0x00262EE8     music_info structure For Drop Out
             0x00162FF0                  0x00262F70     music_info structure For Dynamite Rave
             0x00163078                  0x00262FF8     music_info structure For LOVE ♥ SHINE
             0x00163100                  0x00263080     music_info structure For PARANOiA Survivor
             0x00163188                  0x00263108     music_info structure For PARANOiA Rebirth
             0x00163210                  0x00263190     Empty music_info structure With Name "inst" 
             0x00163298                  0x00263218     Empty music_info structure With Name "name"
             0x00163320                  0x002632A0     Empty music_info structure With Name "scal"
             0x001633A8                  0x00263328     Empty music_info structure With Name "sele"
             0x00163430                  0x002633B0     Empty music_info structure With Name "stae"
             0x001634B8                  0x00263438     Empty music_info structure With Name "staf"
0x001635C8 - 0x0016364C     0x00263548 - 0x002635CC     UNUSED SPACE - 132 BYTES
0x00163650 - 0x0016377C     0x002635D0 - 0x002636FC     Preview Sound Index Array
             0x00163650                  0x002635D0     Preview Sound Index Value For Long Train Runnin'
             0x00163654                  0x002635D4     Preview Sound Index Value For Maximum Overdrive
             0x00163658                  0x002635D8     Preview Sound Index Value For Waka Laka
             0x0016365C                  0x002635DC     Preview Sound Index Value For Baby Love Me
             0x00163660                  0x002635E0     Preview Sound Index Value For D2R
             0x00163664                  0x002635E4     Preview Sound Index Value For Destiny
             0x00163668                  0x002635E8     Preview Sound Index Value For Living In America
             0x0016366C                  0x002635EC     Preview Sound Index Value For Sweet Sweet ♥ Magic
             0x00163670                  0x002635F0     Preview Sound Index Value For Ever Snow
             0x00163674                  0x002635F4     Preview Sound Index Value For AM-3P (303 BASS MIX)
             0x00163678                  0x002635F8     Preview Sound Index Value For The Reflex
             0x0016367C                  0x002635FC     Preview Sound Index Value For So Fabulous So Fierce (Freak Out!)
             0x00163680                  0x00263600     Preview Sound Index Value For Drifting Away
             0x00163684                  0x00263604     Preview Sound Index Value For Stay
             0x00163688                  0x00263608     Preview Sound Index Value For Secret Rendez-vous
             0x0016368C                  0x0026360C     Preview Sound Index Value For Little Boy (Boy Oh Boy Mix)
             0x00163690                  0x00263610     Preview Sound Index Value For Rain of Sorrow
             0x00163694                  0x00263614     Preview Sound Index Value For Maxx Unlimited
             0x00163698                  0x00263618     Preview Sound Index Value For Dive To The Night
             0x0016369C                  0x0026361C     Preview Sound Index Value For Tsugaru
             0x001636A0                  0x00263620     Preview Sound Index Value For BRE∀K DOWN!
             0x001636A4                  0x00263624     Preview Sound Index Value For Burning Heat! (3 Option Mix)
             0x001636A8                  0x00263628     Preview Sound Index Value For Nothing Gonna Stop
             0x001636AC                  0x0026362C     Preview Sound Index Value For Fantasy
             0x001636B0                  0x00263630     Preview Sound Index Value For i feel ...
             0x001636B4                  0x00263634     Preview Sound Index Value For CANDY ♥ 
             0x001636B8                  0x00263638     Preview Sound Index Value For Spin the Disc
             0x001636BC                  0x0026363C     Preview Sound Index Value For Trance De Janeiro
             0x001636C0                  0x00263640     Preview Sound Index Value For Look At Us
             0x001636C4                  0x00263644     Preview Sound Index Value For The Whistle Song (Blow My Whistle Bitch)
             0x001636C8                  0x00263648     Preview Sound Index Value For 革命 (Kakumei)
             0x001636CC                  0x0026364C     Preview Sound Index Value For AFRONOVA (From Nonstop Megamix)
             0x001636D0                  0x00263650     Preview Sound Index Value For AM-3P (AM EAST MIX)
             0x001636D4                  0x00263654     Preview Sound Index Value For Brillant 2U (K.O.G G3 Mix)
             0x001636D8                  0x00263658     Preview Sound Index Value For B4U (B4 ZA BEAT MIX)
             0x001636DC                  0x0026365C     Preview Sound Index Value For DROP OUT (From Nonstop Megamix)
             0x001636E0                  0x00263660     Preview Sound Index Value For Dynamite Rave (B4 ZA BEAT MIX)
             0x001636E4                  0x00263664     Preview Sound Index Value For Hysteria 2001
             0x001636E8                  0x00263668     Preview Sound Index Value For 祭 JAPAN (From Nonstop Megamix)
             0x001636EC                  0x0026366C     Preview Sound Index Value For SEXY PLANET (From Nonstop Megamix)
             0x001636F0                  0x00263670     Preview Sound Index Value For Super Star (From Nonstop Megamix)
             0x001636F4                  0x00263674     Preview Sound Index Value For Still In My Heart (MOMO MIX)
             0x001636F8                  0x00263678     Preview Sound Index Value For Wild Rush (From Nonstop Megamix)
             0x001636FC                  0x0026367C     Preview Sound Index Value For Burnin' The Floor (BLUE Fire mix)
             0x00163700                  0x00263680     Preview Sound Index Value For Tsugaru (Apple Mix)
             0x00163704                  0x00263684     Preview Sound Index Value For Ecstacy (Mifnight Blue Mix)
             0x00163708                  0x00263688     Preview Sound Index Value For Silent Hill (3rd Christmas Mix)
             0x0016370C                  0x0026368C     Preview Sound Index Value For Celebrate Nite (Euro Trance Style)
             0x00163710                  0x00263690     Preview Sound Index Value For Higher (Next Morning Mix)
             0x00163714                  0x00263694     Preview Sound Index Value For My Summer Love (Tommy's Smile Mix)
             0x00163718                  0x00263698     Preview Sound Index Value For Look to the Sky (True Color Mix)
             0x0016371C                  0x0026369C     Preview Sound Index Value For Cutie Chaser (Morning Mix)
             0x00163720                  0x002636A0     Preview Sound Index Value For Do It Right (Harmonized 25step Mix)
             0x00163724                  0x002636A4     Preview Sound Index Value For Drop the Bomb -System S.F Mix-
             0x00163728                  0x002636A8     Preview Sound Index Value For Dynamite Rave (Down Bird SOTA Mix)
             0x0016372C                  0x002636AC     Preview Sound Index Value For I'm For Real
             0x00163730                  0x002636B0     Preview Sound Index Value For Jam & Marmalade
             0x00163734                  0x002636B4     Preview Sound Index Value For Kind Lady
             0x00163738                  0x002636B8     Preview Sound Index Value For Logical Dash
             0x0016373C                  0x002636BC     Preview Sound Index Value For Overblast!!
             0x00163740                  0x002636C0     Preview Sound Index Value For Peace-Out
             0x00163744                  0x002636C4     Preview Sound Index Value For So In Love
             0x00163748                  0x002636C8     Preview Sound Index Value For The Shining Polaris
             0x0016374C                  0x002636CC     Preview Sound Index Value For Look To The Sky (Trance Mix)
             0x00163750                  0x002636D0     Preview Sound Index Value For Do It Right (80s Electro Mix)
             0x00163754                  0x002636D4     Preview Sound Index Value For Kind Lady (Interlude)
             0x00163758                  0x002636D8     Preview Sound Index Value For B4U
             0x0016375C                  0x002636DC     Preview Sound Index Value For Crash!
             0x00163760                  0x002636E0     Preview Sound Index Value For Dead End
             0x00163764                  0x002636E4     Preview Sound Index Value For Drop Out
             0x00163768                  0x002636E8     Preview Sound Index Value For Dynamite Rave
             0x0016376C                  0x002636EC     Preview Sound Index Value For LOVE ♥ SHINE
             0x00163770                  0x002636F0     Preview Sound Index Value For PARANOiA Survivor
             0x00163774                  0x002636F4     Preview Sound Index Value For PARANOiA Rebirth
             0x00163778                  0x002636F8     Empty Preview Sound Index Array Element
             0x0016377C                  0x002636FC     Empty Preview Sound Index Array Element
0x00166DC0 - 0x00166EE4     0x00266D40 - 0x00266E64     Table of addresses pertaining to loading a song's static background image
             0x00166DC0                  0x00266D40     Long Train Runnin' Static Background Image Information Related Address
             0x00166DC4                  0x00266D44     Maximum Overdrive Static Background Image Information Related Address
             0x00166DC8                  0x00266D48     Waka Laka Static Background Image Information Related Address
             0x00166DCC                  0x00266D4C     Baby Love Me Static Background Image Information Related Address
             0x00166DD0                  0x00266D50     D2R Static Background Image Information Related Address
             0x00166DD4                  0x00266D54     Destiny Static Background Image Information Related Address
             0x00166DD8                  0x00266D58     Living In America Static Background Image Information Related Address
             0x00166DDC                  0x00266D5C     Sweet Sweet ? Magic Static Background Image Information Related Address
             0x00166DE0                  0x00266D60     Ever Snow Static Background Image Information Related Address
             0x00166DE4                  0x00266D64     AM-3P (303 BASS MIX) Static Background Image Information Related Address
             0x00166DE8                  0x00266D68     The Reflex Static Background Image Information Related Address
             0x00166DEC                  0x00266D6C     So Fabulous So Fierce (Freak Out!) Static Background Image Information Related Address
             0x00166DF0                  0x00266D70     Drifting Away Static Background Image Information Related Address
             0x00166DF4                  0x00266D74     Stay Static Background Image Information Related Address
             0x00166DF8                  0x00266D78     Secret Rendez-vous Static Background Image Information Related Address
             0x00166DFC                  0x00266D7C     Little Boy (Boy Oh Boy Mix) Static Background Image Information Related Address
             0x00166E00                  0x00266D80     Rain of Sorrow Static Background Image Information Related Address
             0x00166E04                  0x00266D84     Maxx Unlimited Static Background Image Information Related Address
             0x00166E08                  0x00266D88     Dive To The Night Static Background Image Information Related Address
             0x00166E0C                  0x00266D8C     Tsugaru Static Background Image Information Related Address
             0x00166E10                  0x00266D90     BRE?K DOWN! Static Background Image Information Related Address
             0x00166E14                  0x00266D94     Burning Heat! (3 Option Mix) Static Background Image Information Related Address
             0x00166E18                  0x00266D98     Nothing Gonna Stop Static Background Image Information Related Address
             0x00166E1C                  0x00266D9C     Fantasy Static Background Image Information Related Address
             0x00166E20                  0x00266DA0     i feel ... Static Background Image Information Related Address
             0x00166E24                  0x00266DA4     CANDY ?  Static Background Image Information Related Address
             0x00166E28                  0x00266DA8     Spin the Disc Static Background Image Information Related Address
             0x00166E2C                  0x00266DAC     Trance De Janeiro Static Background Image Information Related Address
             0x00166E30                  0x00266DB0     Look At Us Static Background Image Information Related Address
             0x00166E34                  0x00266DB4     The Whistle Song (Blow My Whistle Bitch) Static Background Image Information Related Address
             0x00166E38                  0x00266DB8     ?? (Kakumei) Static Background Image Information Related Address
             0x00166E3C                  0x00266DBC     AFRONOVA (From Nonstop Megamix) Static Background Image Information Related Address
             0x00166E40                  0x00266DC0     AM-3P (AM EAST MIX) Static Background Image Information Related Address
             0x00166E44                  0x00266DC4     Brillant 2U (K.O.G G3 Mix) Static Background Image Information Related Address
             0x00166E48                  0x00266DC8     B4U (B4 ZA BEAT MIX) Static Background Image Information Related Address
             0x00166E4C                  0x00266DCC     DROP OUT (From Nonstop Megamix) Static Background Image Information Related Address
             0x00166E50                  0x00266DD0     Dynamite Rave (B4 ZA BEAT MIX) Static Background Image Information Related Address
             0x00166E54                  0x00266DD4     Hysteria 2001 Static Background Image Information Related Address
             0x00166E58                  0x00266DD8     ? JAPAN (From Nonstop Megamix) Static Background Image Information Related Address
             0x00166E5C                  0x00266DDC     SEXY PLANET (From Nonstop Megamix) Static Background Image Information Related Address
             0x00166E60                  0x00266DE0     Super Star (From Nonstop Megamix) Static Background Image Information Related Address
             0x00166E64                  0x00266DE4     Still In My Heart (MOMO MIX) Static Background Image Information Related Address
             0x00166E68                  0x00266DE8     Wild Rush (From Nonstop Megamix) Static Background Image Information Related Address
             0x00166E6C                  0x00266DEC     Burnin' The Floor (BLUE Fire mix) Static Background Image Information Related Address
             0x00166E70                  0x00266DF0     Tsugaru (Apple Mix) Static Background Image Information Related Address
             0x00166E74                  0x00266DF4     Ecstacy (Mifnight Blue Mix) Static Background Image Information Related Address
             0x00166E78                  0x00266DF8     Silent Hill (3rd Christmas Mix) Static Background Image Information Related Address
             0x00166E7C                  0x00266DFC     Celebrate Nite (Euro Trance Style) Static Background Image Information Related Address
             0x00166E80                  0x00266E00     Higher (Next Morning Mix) Static Background Image Information Related Address
             0x00166E84                  0x00266E04     My Summer Love (Tommy's Smile Mix) Static Background Image Information Related Address
             0x00166E88                  0x00266E08     Look to the Sky (True Color Mix) Static Background Image Information Related Address
             0x00166E8C                  0x00266E0C     Cutie Chaser (Morning Mix) Static Background Image Information Related Address
             0x00166E90                  0x00266E10     Do It Right (Harmonized 25step Mix) Static Background Image Information Related Address
             0x00166E94                  0x00266E14     Drop the Bomb -System S.F Mix- Static Background Image Information Related Address
             0x00166E98                  0x00266E18     Dynamite Rave (Down Bird SOTA Mix) Static Background Image Information Related Address
             0x00166E9C                  0x00266E1C     I'm For Real Static Background Image Information Related Address
             0x00166EA0                  0x00266E20     Jam & Marmalade Static Background Image Information Related Address
             0x00166EA4                  0x00266E24     Kind Lady Static Background Image Information Related Address
             0x00166EA8                  0x00266E28     Logical Dash Static Background Image Information Related Address
             0x00166EAC                  0x00266E2C     Overblast!! Static Background Image Information Related Address
             0x00166EB0                  0x00266E30     Peace-Out Static Background Image Information Related Address
             0x00166EB4                  0x00266E34     So In Love Static Background Image Information Related Address
             0x00166EB8                  0x00266E38     The Shining Polaris Static Background Image Information Related Address
             0x00166EBC                  0x00266E3C     Look To The Sky (Trance Mix) Static Background Image Information Related Address
             0x00166EC0                  0x00266E40     Do It Right (80s Electro Mix) Static Background Image Information Related Address
             0x00166EC4                  0x00266E44     Kind Lady (Interlude) Static Background Image Information Related Address
             0x00166EC8                  0x00266E48     B4U Static Background Image Information Related Address
             0x00166ECC                  0x00266E4C     Crash! Static Background Image Information Related Address
             0x00166ED0                  0x00266E50     Dead End Static Background Image Information Related Address
             0x00166ED4                  0x00266E54     Drop Out Static Background Image Information Related Address
             0x00166ED8                  0x00266E58     Dynamite Rave Static Background Image Information Related Address
             0x00166EDC                  0x00266E5C     LOVE ? SHINE Static Background Image Information Related Address
             0x00166EE0                  0x00266E60     PARANOiA Survivor Static Background Image Information Related Address
             0x00166EE4                  0x00266E64     PARANOiA Rebirth Static Background Image Information Related Address
0x001690A0 - 0x001696A4     0x00269020 - 0x00269624     oni_steps[77] oni_steps_table
             0x001690A0                  0x00269020     oni_steps data for Long Train Runnin'
             0x001690B4                  0x00269034     oni_steps data for Maximum Overdrive
             0x001690C8                  0x00269048     oni_steps data for
             0x001690DC                  0x0026905C     oni_steps data for
             0x001690F0                  0x00269070     oni_steps data for
             0x00169104                  0x00269084     oni_steps data for
             0x00169118                  0x00269098     oni_steps data for
             0x0016912C                  0x002690AC     oni_steps data for
             0x00169140                  0x002690C0     oni_steps data for
             0x00169154                  0x002690D4     oni_steps data for
             0x00169168                  0x002690E8     oni_steps data for
             0x0016917C                  0x002690FC     oni_steps data for
             0x00169190                  0x00269110     oni_steps data for
             0x001691A4                  0x00269124     oni_steps data for
             0x001691B8                  0x00269138     oni_steps data for
             0x001691CC                  0x0026914C     oni_steps data for
             0x001691E0                  0x00269160     oni_steps data for
             0x001691F4                  0x00269174     oni_steps data for
             0x00169208                  0x00269188     oni_steps data for
             0x0016921C                  0x0026919C     oni_steps data for
             0x00169230                  0x002691B0     oni_steps data for
             0x00169244                  0x002691C4     oni_steps data for
             0x00169258                  0x002691D8     oni_steps data for
             0x0016926C                  0x002691EC     oni_steps data for
             0x00169280                  0x00269200     oni_steps data for
             0x00169294                  0x00269214     oni_steps data for
             0x001692A8                  0x00269228     oni_steps data for
             0x001692BC                  0x0026923C     oni_steps data for
             0x001692D0                  0x00269250     oni_steps data for
             0x001692E4                  0x00269264     oni_steps data for
             0x001692F8                  0x00269278     oni_steps data for
             0x0016930C                  0x0026928C     oni_steps data for
             0x00169320                  0x002692A0     oni_steps data for
             0x00169334                  0x002692B4     oni_steps data for
             0x00169348                  0x002692C8     oni_steps data for
             0x0016935C                  0x002692DC     oni_steps data for
             0x00169370                  0x002692F0     oni_steps data for
             0x00169384                  0x00269304     oni_steps data for
             0x00169398                  0x00269318     oni_steps data for
             0x001693AC                  0x0026932C     oni_steps data for
             0x001693C0                  0x00269340     oni_steps data for
             0x001693D4                  0x00269354     oni_steps data for
             0x001693E8                  0x00269368     oni_steps data for
             0x001693FC                  0x0026937C     oni_steps data for
             0x00169410                  0x00269390     oni_steps data for
             0x00169424                  0x002693A4     oni_steps data for
             0x00169438                  0x002693B8     oni_steps data for
             0x0016944C                  0x002693CC     oni_steps data for
             0x00169460                  0x002693E0     oni_steps data for
             0x00169474                  0x002693F4     oni_steps data for
             0x00169488                  0x00269408     oni_steps data for
             0x0016949C                  0x0026941C     oni_steps data for
             0x001694B0                  0x00269430     oni_steps data for
             0x001694C4                  0x00269444     oni_steps data for
             0x001694D8                  0x00269458     oni_steps data for
             0x001694EC                  0x0026946C     oni_steps data for
             0x00169500                  0x00269480     oni_steps data for
             0x00169514                  0x00269494     oni_steps data for
             0x00169528                  0x002694A8     oni_steps data for
             0x0016953C                  0x002694BC     oni_steps data for
             0x00169550                  0x002694D0     oni_steps data for
             0x00169564                  0x002694E4     oni_steps data for
             0x00169578                  0x002694F8     oni_steps data for
             0x0016958C                  0x0026950C     oni_steps data for
             0x001695A0                  0x00269520     oni_steps data for
             0x001695B4                  0x00269534     oni_steps data for
             0x001695C8                  0x00269548     oni_steps data for
             0x001695DC                  0x0026955C     oni_steps data for
             0x001695F0                  0x00269570     oni_steps data for
             0x00169604                  0x00269584     oni_steps data for
             0x00169618                  0x00269598     oni_steps data for
             0x0016962C                  0x002695AC     oni_steps data for
             0x00169640                  0x002695C0     oni_steps data for
             0x00169654                  0x002695D4     oni_steps data for
             0x00169668                  0x002695E8     oni_steps data for
             0x0016967C                  0x002695FC     oni_steps data for
             0x00169690                  0x00269610     oni_steps data for
0x0016D180 - 0x0016D194     0x0026D100 - 0x0026D114     In-Stage Timing Judgment Label Widths
0x0016D6B0 - 0x0016D6BC     0x0026D630 - 0x0026D63C     Step Judgment Timing Windows - Lower Bounds
             0x0016D6B0                  0x0026D630     Timing Windows Lower Bounds For Perfects  | A value of -5
             0x0016D6B4                  0x0026D634     Timing Windows Lower Bounds For Greats    | A value of -14
             0x0016D6B8                  0x0026D638     Timing Windows Lower Bounds For Goods     | A value of -20
             0x0016D6BC                  0x0026D63C     Timing Windows Lower Bounds For Boos      | A value of -24
             0x0016D6C0                  0x0026D640     Timing Windows Lower Bounds For Misses    | A value of 1
             0x0016D6C4                  0x0026D644     Empty Timing Window Value
             0x0016D6C8                  0x0026D648     Empty Timing Window Value
             0x0016D6CC                  0x0026D64C     Empty Timing Window Value
0x0016D6D0 - 0x0016D6EC     0x0026D650 - 0x0026D66C     Step Judgement Timing Windows - Upper Bounds
             0x0016D6D0                  0x0026D650     Timing Windows Upper Bounds For Perfects   | A value of 6
             0x0016D6D4                  0x0026D654     Timing Windows Upper Bounds For Greats     | A value of 13
             0x0016D6D8                  0x0026D658     Timing Windows Upper Bounds For Goods      | A value of 19 
             0x0016D6DC                  0x0026D65C     Timing Windows Upper Bounds For Boos       | A value of 29 
             0x0016D6E0                  0x0026D660     Timing Windows Upper Bounds For Misses     | A value of -1 
             0x0016D6E4                  0x0026D664     Empty Timing Window Value
             0x0016D6E8                  0x0026D668     Empty Timing Window Value
             0x0016D6EC                  0x0026D66C     Empty Timing Window Value
0x0016D6F0 - 0x0016D71C     0x0026D670 - 0x0026D69C     Dance Point Multipliers    
             0x0016D6F0                  0x0026D670     D.P Multiplier For Perfects                | A value of 2
             0x0016D6F4                  0x0026D674     D.P Multiplier For Greats                  | A value of 1
             0x0016D6F8                  0x0026D678     D.P Multiplier For Goods                   | A value of 0
             0x0016D6FC                  0x0026D67C     D.P Multiplier For Boos                    | A value of -4
             0x0016D700                  0x0026D680     D.P Multiplier For Misses                  | A value of -8                           
             0x0016D704                  0x0026D684     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x0016D708                  0x0026D688     D.P Multiplier for the TOTAL_STEPS count   | A value of 2 
             0x0016D710                  0x0026D690     D.P Multiplier For OKs                     | A value of 6
             0x0016D714                  0x0026D694     -EXACT USE NOT YET KNOWN-                  | A value of 0
             0x0016D718                  0x0026D698     D.P Multiplier For N.Gs?                   | A value of 0
             0x0016D71C                  0x0026D69C     D.P Multiplier for the TOTAL_FREEZ count   | A value of 6

0x0016D978 - 0x0016DA2B     0x0026D8F8 - 0x0026D9AB     Censored Word List For Oni Mode Name Entry
0x0016E290 - 0x0016E2B4     0x0026E210 - 0x0026E234     Jump Table - Title Screen Menu Navigation Options
             0x0016E290                  0x0026E210     Menu Choice For Game Mode
             0x0016E294                  0x0026E214     Menu Choice For Diet Mode
             0x0016E298                  0x0026E218     Brings you back to the main menu.  Could be unused Lesson Mode option? (SPECULATION!!)
             0x0016E29C                  0x0026E21C     Menu Choice For Training Mode
             0x0016E2A0                  0x0026E220     Menu Choice For Edit Mode
             0x0016E2A4                  0x0026E224     Menu Choice For Options  
             0x0016E2A8                  0x0026E228     Menu Choice For Records
             0x0016E2AC                  0x0026E22C     Menu Choice For Information   
             0x0016E2B0                  0x0026E230     Menu Choice For Endless Mode
             0x0016E2B4                  0x0026E234     EMPTY/UNUSE
0x0017C5B0 - 0x0017C714     0x0027C530 - 0x0027C694     Jump Table - Purpose TBD
0x0017DDE8 - 0x0017F2F8     0x0027DD68 - 0x0027F278     Filedata Entry Table
0x0017F602 - 0x001DAC88        NO LOGICAL ADDRESSES     Leftover Debugging Data.  Not Recognized By IDA, PS2DIS, Etc.  DWARF 1.0/1/1 format.
                                                        NOTE: DIE entity info actually starts at 0x0017F640.
</pre>
