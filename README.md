select 
F.PROCESS_DATE   AS  TARIH,
F.ACCOUNT_NUM   AS  HESAP_NO,
F.GL_ACCOUNT_NUM   AS  DK_NUMARASI,
F.CUSTOMER_NUM   AS  MUSTERI_NO,
C.CUSTOMER_LONG_NAME   AS  MUSTERI_ADI,
C.COUNTRY_OF_RES_ID    AS  ULKE,
C.RISK_GROUP_CODE   AS  RGK,
F.BRANCH_ID   AS  SUBE_KODU,
F.CURR_CODE   AS  PARA_KODU,
F.BALANCE_AMNT   AS  BAKIYE_ORJ,
F.TL_BALANCE_AMNT_GISE   AS  BAKIYE_TL,
F.OPEN_DATE   AS  ACILIS_TARIHI,
F.DUE_DATE   AS  VADE_TARIHI,
F.INTEREST_RATE   AS  FAIZ_ORANI,
F.COMPOUND_INTEREST   AS  BILESIK_FAIZ,
F.REDISCOUNT_AMNT   AS  REESKONT_TUTARI,
F.INTEREST_CALC_TYPE   AS  FAIZ_TIP,
F.SWIFT_CODE   AS  SWIFT,
C.SECTOR_CODE   AS  NACE_KOD,
C.FINANCE_CODE   AS  FKK
 from
TGARYSR.TDM_FIN_INST_ACCOUNT_ALL F
left join TGARYSR.TDWINPA C
on F.PROCESS_DATE=C.PROCESS_DATE
and F.CUSTOMER_NUM=C.IP_ID
WHERE 
F.PROCESS_DATE = TO_DATE(20240831,'YYYYMMDD')
AND F.BALANCE_AMNT<>0
AND F.CLOSED_IND ='A'

bankalar detay
