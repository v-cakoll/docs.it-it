---
title: 'Procedura: usare Svcutil.exe per convalidare il codice del servizio compilato'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 6f2064c696e3186c3208a7e57dc51655056d23ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595349"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Procedura: usare Svcutil.exe per convalidare il codice del servizio compilato
È possibile utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per rilevare gli errori nelle configurazioni e nelle implementazioni del servizio senza ospitare il servizio.  
  
### <a name="to-validate-a-service"></a>Per convalidare un servizio  
  
1. Compilare il servizio in un file eseguibile e in uno o più assembly dipendenti.  
  
2. Aprire un prompt dei comandi SDK.  
  
3. Al prompt dei comandi, avviare lo strumento Svcutil.exe usando il formato seguente. Per ulteriori informazioni sui vari parametri, vedere l'argomento Service Validationsection dell'argomento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) .  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     È necessario usare l'opzione `/serviceName` per indicare il nome di configurazione del servizio che si desidera convalidare.  
  
     L'argomento `assemblyPath` specifica il percorso del file eseguibile per il servizio e uno o più assembly che contengono i tipi di servizio da convalidare. L'assembly eseguibile deve avere un file di configurazione associato per fornire la configurazione del servizio. È possibile usare caratteri jolly della riga di comando standard per fornire più assembly.  
  
## <a name="example"></a>Esempio  
 Il comando seguente implementa il servizio myServiceName nel file eseguibile myServiceHost.exe.  Il file di configurazione per il servizio (myServiceHost.exe.config) viene automaticamente caricato.  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
