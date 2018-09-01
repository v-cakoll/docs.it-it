---
title: Requisiti di sistema per il provider di dati.NET Framework per Oracle
ms.date: 03/30/2017
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
ms.openlocfilehash: 60d57e30e2a1588ec6e0b9e253f371f8fbae28bc
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385747"
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a>Requisiti di sistema per il provider di dati.NET Framework per Oracle
Per usare il provider di dati .NET Framework per Oracle, è necessario disporre di Microsoft Data Access Components (MDAC) 2.6 o versione successiva. Si consiglia l'uso di MDAC 2.8 SP1.  
  
 È inoltre necessario installare il client Oracle 8i Release 3 (8.1.7) o versione successiva.  
  
 Non è possibile eseguire l'accesso ai database UTF16 mediante i software client Oracle precedenti alla versione Oracle 9i in quanto UTF16 è una nuova funzione di Oracle 9i. Per usare questa funzione, è necessario aggiornare il software client alla versione Oracle 9i o versione successiva.  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a>Utilizzo del provider di dati per dati Oracle e Unicode  
 Di seguito è riportato un elenco di problemi relativi a Unicode da tenere presente quando si usano il provider di dati .NET Framework per Oracle e le librerie del client Oracle. Per altre informazioni, vedere la documentazione di Oracle.  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a>Impostazione del valore Unicode in un attributo della stringa di connessione  
 Quando si usa Oracle, è possibile usare l'attributo della stringa di connessione   
  
```  
Unicode=True   
```  
  
 per l'inizializzazione delle librerie del client Oracle in modalità UTF-16. In questo modo le librerie del client Oracle accetteranno stringhe UTF-16 (molto simili a quelle UCS-12) anziché multibyte. Ciò consente al provider di dati per Oracle di usare qualsiasi pagina di codice Oracle senza eseguire ulteriori operazioni di conversione. Questa configurazione è utile solo se per la comunicazione con un database Oracle 9i viene usato un client Oracle 9i e un set di caratteri alternativo di AL16UTF16. Quando un client Oracle 9i comunica con un server Oracle 9i, sono necessarie risorse aggiuntive per convertire la versione Unicode **CommandText** i valori per i caratteri multibyte appropriato impostare che il Oracle9i Usa server. Questo può essere evitato se si è certi di disporre della configurazione corretta, aggiungendo `Unicode=True` alla stringa di connessione.  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a>Combinazione di versioni del client e del server Oracle  
 Non possono accedere i client Oracle 8i **NCHAR**, **NVARCHAR2**, o **NCLOB** dati nel database Oracle 9i quando il set di caratteri nazionale del server specificato è AL16UTF16 (il impostazione predefinita di Oracle 9i). poiché il supporto del set di caratteri UTF-16 è stato introdotto solo con Oracle 9i.  
  
### <a name="working-with-utf-8-data"></a>Uso di dati UTF-8  
 Per impostare il set di caratteri alternativo, impostare la chiave del Registro di sistema HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG su UTF8. Per altre informazioni, vedere le note di installazione di Oracle sulla piattaforma. L'impostazione predefinita corrisponde al set di caratteri primario della lingua in cui si esegue l'installazione del software client Oracle. Se la lingua non viene impostata in modo che corrisponda al set di caratteri della lingua nazionale del database al quale si esegue la connessione, i dati inviati e ricevuti dall'associazione delle colonne e dei parametri saranno basati sul set di caratteri del database primario anziché sul set di caratteri nazionale.  
  
### <a name="oraclelob-can-only-update-full-characters"></a>OracleLob consente di aggiornare solo caratteri completi.  
 Per motivi di usabilità, la <xref:System.Data.OracleClient.OracleLob> oggetto eredita dalla classe Stream di .NET Framework e fornisce **ReadByte** e **WriteByte** metodi. Implementa inoltre metodi, ad esempio **CopyTo** e **Erase**, che usare sulle sezioni di Oracle **LOB** oggetti. Al contrario, il software client Oracle fornisce una serie di API per l'uso con **LOB**s (**CLOB** e **NCLOB**). Tuttavia, queste API funzionano solo con i caratteri completi. A causa di questa differenza, il Provider di dati per Oracle implementa il supporto per **Read** e **ReadByte** per lavorare con dati UTF-16 in una modalità byte per byte. Tuttavia, gli altri metodi del **OracleLob** oggetto consentono solo operazioni con caratteri completi.  
  
## <a name="see-also"></a>Vedere anche  
 [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
