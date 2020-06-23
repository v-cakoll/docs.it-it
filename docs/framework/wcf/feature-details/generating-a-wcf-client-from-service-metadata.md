---
title: Generazione di un client WCF dai metadati del servizio
description: Individuare le varie opzioni di Svcutil.exe utilizzate per generare client WFC da documenti di metadati del servizio in base a WSDL o a un file di criteri dal servizio.
ms.date: 03/30/2017
ms.assetid: 27f8f545-cc44-412a-b104-617e0781b803
ms.openlocfilehash: f755a092fb3596349a6878c61fe414f4e0a9f9d1
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247273"
---
# <a name="generating-a-wcf-client-from-service-metadata"></a>Generazione di un client WCF dai metadati del servizio
In questo argomento viene illustrato come utilizzare le varie opzioni in Svcutil.exe per generare client da documenti dei metadati.  
  
 Questi documenti dei metadati possono essere salvati in modo permanente o recuperati in linea. Il recupero in linea segue il protocollo WS-MetadataExchange o il protocollo Microsoft Discovery (DISCO). Per recuperare metadati, Svcutil.exe genera contemporaneamente le richieste di metadati seguenti:  
  
- Richiesta WS-MetadataExchange (MEX) all'indirizzo fornito.  
  
- Richiesta MEX all'indirizzo fornito con `/mex` accodato.  
  
- Richiesta DISCO (usando <xref:System.Web.Services.Discovery.DiscoveryClientProtocol> da ASP.NET Web Services) all'indirizzo fornito.  
  
 Lo strumento Svcutil.exe consente di generare il client in base al WSDL (Web Services Description Language) o al file dei criteri ricevuto dal servizio. Il nome dell'entità utente (UPN) viene generato concatenando il nome utente con " \@ " e quindi aggiungendo un nome di dominio completo (FQDN). Tuttavia, per gli utenti che hanno eseguito la registrazione in Active Directory, questo formato non è valido e l'UPN generato dallo strumento provoca un errore nell'autenticazione Kerberos con il messaggio di errore seguente: **tentativo di accesso non riuscito.** Per risolvere questo problema, è necessario correggere manualmente il file client generato da questo strumento.  
  
```console
svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>  
```  
  
## <a name="referencing-and-sharing-types"></a>Riferimento e condivisione dei tipi  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/Reference\<file path>**|Fa riferimento a tipi nell'assembly specificato. Quando si generano client, utilizzare questa opzione per specificare assembly che potrebbero contenere tipi che rappresentano i metadati importati.<br /><br /> Forma abbreviata: `/r`|  
|**/excludeType:\<type>**|Specifica un nome tipo completo o un nome completo del tipo dell’assembly da escludere dai tipi di contratto a cui si fa riferimento.<br /><br /> Forma abbreviata: `/et`|  
  
## <a name="choosing-a-serializer"></a>Scelta di un serializzatore  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/serializer:Auto**|Seleziona automaticamente il serializzatore. Utilizza il serializzatore `DataContract`. In caso di errore, viene utilizzato `XmlSerializer`.<br /><br /> Forma abbreviata: `/ser:Auto`|  
|**/serializer:DataContractSerializer**|Generare tipi di dati che utilizzano il serializzatore `DataContract` per la serializzazione e la deserializzazione.<br /><br /> Forma abbreviata: `/ser:DataContractSerializer`|  
|**/serializer:XmlSerializer**|Genera tipi di dati che utilizzano `XmlSerializer` per la serializzazione e la deserializzazione.<br /><br /> Forma abbreviata: `/ser:XmlSerializer`|  
|**/importXmlTypes**|Configura il serializzatore `DataContract` per importare tipi non `DataContract` come tipi `IXmlSerializable`.<br /><br /> Forma abbreviata: `/ixt`|  
|**/dataContractOnly**|Genera codice solo per i tipi `DataContract`. Vengono generati i tipi `ServiceContract`.<br /><br /> Per questa opzione è necessario specificare soltanto file di metadati locali.<br /><br /> Forma abbreviata: `/dconly`|  
  
## <a name="choosing-a-language-for-the-client"></a>Scelta di un linguaggio per il client  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/Language\<language>**|Specifica il linguaggio di programmazione da utilizzare per la generazione del codice. Fornire un nome di linguaggio registrato nel file Machine.config o il nome completo di una classe che eredita da <xref:System.CodeDom.Compiler.CodeDomProvider>.<br /><br /> Valori: c#, cs, csharp, vb, vbs, visualbasic, vbscript, javascript, c++, mc, cpp<br /><br /> Impostazione predefinita: csharp<br /><br /> Forma abbreviata: `/l`<br /><br /> Per ulteriori informazioni, vedere la classe <xref:System.CodeDom.Compiler.CodeDomProvider>.|  
  
## <a name="choosing-a-namespace-for-the-client"></a>Scelta di uno spazio dei nomi per il client  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/namespace\<string,string>**|Specifica un mapping da un WSDL o XML Schema `targetNamespace` a uno spazio dei nomi Common Language Runtime (CLR). L’utilizzo di un carattere jolly (*) per `targetNamespace` consente di eseguire il mapping di tutti i `targetNamespaces` senza un mapping esplicito a quello spazio dei nomi CLR.<br /><br /> Per assicurarsi che il nome del contratto di messaggio non entri in conflitto con il nome dell'operazione, è necessario qualificare il riferimento al tipo con doppi due punti (`::`) o verificare che i nomi siano univoci.<br /><br /> Impostazione predefinita: derivata dallo spazio dei nomi di destinazione del documento dello schema per `DataContracts`. Lo spazio dei nomi predefinito viene utilizzato per tutti gli altri tipi generati.<br /><br /> Forma abbreviata: `/n`|  
  
## <a name="choosing-a-data-binding"></a>Scelta di un data binding  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/enableDataBinding**|Implementa l'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged> su tutti i tipi `DataContract` per consentire il data binding.<br /><br /> Forma abbreviata: `/edb`|  
  
## <a name="generating-configuration"></a>Generazione della configurazione  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/config\<configFile>**|Specifica il nome file per il file di configurazione generato.<br /><br /> Impostazione predefinita: output.config|  
|**/mergeConfig**|Incorpora la configurazione generata in un file esistente, anziché sovrascrivere il file esistente.|  
|**/noConfig**|Non genera file di configurazione.|  
  
## <a name="see-also"></a>Vedere anche

- [Uso di metadati](using-metadata.md)
- [Panoramica dell'architettura dei metadati](metadata-architecture-overview.md)
