---
title: "Utilità client WCF Data Services (DataSvcUtil.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21189ffd5fc8b113cc746fd855bd5c325aad78c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Utilità client WCF Data Services (DataSvcUtil.exe)
DataSvcUtil.exe è uno strumento da riga di comando fornito da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] che utilizza un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed e genera le classi del servizio dati client necessarie per accedere a un servizio dati da un'applicazione client .NET Framework. Questa utilità consente di generare classi di dati usando le origini di metadati seguenti:  
  
-   L'URI radice di un servizio dati. L'utilità richiede il documento dei metadati del servizio che descrive il modello di dati esposto dal servizio dati. Per ulteriori informazioni, vedere [OData: documento dei metadati del servizio](http://go.microsoft.com/fwlink/?LinkId=186070).  
  
-   Un file di modello di dati (con estensione CSDL) definito tramite lo schema conceptual schema definition language (CSDL), come definito nel [ \[MC-CSDL\]: formato di File di definizione dello Schema concettuale](http://go.microsoft.com/fwlink/?LinkID=159072) specifica.  
  
-   Un file con estensione edmx creato usando gli strumenti di Entity Data Model forniti con Entity Framework. Per ulteriori informazioni, vedere il [ \[MC-EDMX\]: Entity Data Model per il formato dei pacchetti di servizi dati](http://go.microsoft.com/fwlink/?LinkID=178833) specifica.  
  
 Per ulteriori informazioni, vedere [come: manualmente generare classi servizio dati Client](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
 Lo strumento DataSvcUtil.exe viene installato nella directory [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. In molti casi, il file si trova in C:\Windows\Microsoft.NET\Framework\v4.0. Per i sistemi a 64 bit, questa directory si trova in C:\Windows\Microsoft.NET\Framework64\v4.0. È inoltre possibile accedere lo strumento DataSvcUtil.exe dal prompt dei comandi di Visual Studio (fare clic su **avviare**, scegliere **tutti i programmi**, scegliere **Microsoft Visual Studio 2010**, Scegliere **Visual Studio Tools**, quindi fare clic su **Prompt dei comandi di Visual Studio 2010**).  
  
## <a name="syntax"></a>Sintassi  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|`/dataservicecollection`|Indica che verrà generato anche il codice necessario per l'associazione di oggetti a controlli.|  
|`/help`<br /><br /> -oppure-<br /><br /> `/?`|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|`/in:` *\<file >*|Consente di specificare il file con estensione csdl o edmx oppure una directory in cui si trova il file.|  
|`/language:`[VB &#124; CSharp]|Consente di specificare il linguaggio per i file di codice sorgente generati. Il linguaggio predefinito è C#.|  
|`/nologo`|Consente di disattivare la visualizzazione del messaggio di copyright.|  
|`/out:` *\<file >*|Consente di specificare il nome del file di codice sorgente contenente le classi del servizio dati client generate.|  
|`/uri:` *\<stringa >*|L'URI del [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.|  
|`/version:`[1.0&#124;2.0]|Consente di specificare la versione accettata più recente di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. La versione viene determinata in base il `DataServiceVersion` attributo dell'elemento DataService nei metadati del servizio dati restituiti. Per ulteriori informazioni, vedere [controllo delle versioni del servizio dati](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Quando si specifica il `/dataservicecollection` parametro, è necessario specificare anche `/version:2.0` per consentire l'associazione dati.|  
  
## <a name="see-also"></a>Vedere anche  
 [Generazione della libreria client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [Procedura: aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
