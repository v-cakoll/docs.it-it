---
title: Requisiti di sistema per il provider di dati.NET Framework per Oracle
ms.date: 03/30/2017
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
ms.openlocfilehash: dab3378d3022c01c674640201a67f3bdbb4f571f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174251"
---
# <a name="system-requirements-for-the-net-framework-data-provider-for-oracle"></a>Requisiti di sistema per il provider di dati.NET Framework per Oracle

Per usare il provider di dati .NET Framework per Oracle, è necessario disporre di Microsoft Data Access Components (MDAC) 2.6 o versione successiva. Si consiglia l'uso di MDAC 2.8 SP1.  
  
 È inoltre necessario installare il client Oracle 8i Release 3 (8.1.7) o versione successiva.  
  
 Non è possibile eseguire l'accesso ai database UTF16 mediante i software client Oracle precedenti alla versione Oracle 9i in quanto UTF16 è una nuova funzionalità di Oracle 9i. Per usare questa funzionalità, è necessario aggiornare il software client alla versione Oracle 9i o versione successiva.  
  
## <a name="working-with-the-data-provider-for-oracle-and-unicode-data"></a>Utilizzo del provider di dati per dati Oracle e Unicode  

Di seguito è riportato un elenco dei problemi relativi a Unicode che è necessario considerare quando si lavora con il provider di dati .NET Framework per le librerie client Oracle e Oracle. Per altre informazioni, vedere la documentazione di Oracle.  
  
### <a name="setting-the-unicode-value-in-a-connection-string-attribute"></a>Impostazione del valore Unicode in un attributo della stringa di connessione  

Quando si usa Oracle, è possibile usare l'attributo della stringa di connessione   
  
`Unicode=True`
  
per l'inizializzazione delle librerie del client Oracle in modalità UTF-16. In questo modo le librerie del client Oracle accetteranno stringhe UTF-16 (molto simili a quelle UCS-12) anziché multibyte. Ciò consente al provider di dati per Oracle di usare qualsiasi pagina di codice Oracle senza eseguire ulteriori operazioni di conversione. Questa configurazione è utile solo se per la comunicazione con un database Oracle 9i viene usato un client Oracle 9i e un set di caratteri alternativo di AL16UTF16. Quando un client Oracle 9i comunica con un server Oracle 9i, sono necessarie risorse aggiuntive per convertire i valori **Unicode CommandText** nel set di caratteri multibyte appropriato utilizzato dal server Oracle9i. Questo può essere evitato se si è certi di disporre della configurazione corretta, aggiungendo `Unicode=True` alla stringa di connessione.  
  
### <a name="mixing-versions-of-oracle-client-and-oracle-server"></a>Combinazione di versioni del client e del server Oracle  

I client Oracle 8i non possono accedere ai dati **NCHAR**, **NVARCHAR2**o **NCLOB** nei database Oracle 9i quando il set di caratteri nazionali del server è specificato come AL16UTF16 (impostazione predefinita per Oracle 9i). poiché il supporto del set di caratteri UTF-16 è stato introdotto solo con Oracle 9i.  
  
### <a name="working-with-utf-8-data"></a>Uso di dati UTF-8  

Per impostare il set di caratteri alternativo, impostare la chiave del Registro di sistema HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE\HOMEID\NLS_LANG su UTF8. Per altre informazioni, vedere le note di installazione di Oracle sulla piattaforma. L'impostazione predefinita corrisponde al set di caratteri primario della lingua in cui si esegue l'installazione del software client Oracle. Se la lingua non viene impostata in modo che corrisponda al set di caratteri della lingua nazionale del database al quale si esegue la connessione, i dati inviati e ricevuti dall'associazione delle colonne e dei parametri saranno basati sul set di caratteri del database primario anziché sul set di caratteri nazionale.  
  
### <a name="oraclelob-can-only-update-full-characters"></a>OracleLob consente di aggiornare solo caratteri completi.  

Per motivi di <xref:System.Data.OracleClient.OracleLob> usabilità, l'oggetto eredita dalla classe Stream di .NET Framework e fornisce metodi **ReadByte** e **WriteByte** . Implementa inoltre metodi, ad esempio **CopyTo** e **Erase**, che funzionano su sezioni di oggetti **LOB** Oracle. Al contrario, il software client Oracle fornisce una serie di API per lavorare con i **caratteri LOB**s (**CLOB** e **NCLOB**). Tuttavia, queste API funzionano solo con i caratteri completi. A causa di questa differenza, il provider di dati per Oracle implementa il supporto per **Read** e **ReadByte** per lavorare con i dati UTF-16 in modo byte-wise. Tuttavia, gli altri metodi dell'oggetto **OracleLob** consentono solo operazioni con caratteri completi.  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](oracle-and-adonet.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
