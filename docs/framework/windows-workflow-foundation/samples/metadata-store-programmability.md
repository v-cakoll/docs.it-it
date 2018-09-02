---
title: Programmabilità dell'archivio di metadati
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43423285"
---
# <a name="metadata-store-programmability"></a>Programmabilità dell'archivio di metadati
L'archivio di metadati è una funzionalità di [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] che consente l'associazione di metadati arbitrari, nel formato di attributi CLR, ai tipi in fase di esecuzione. In questo modo è possibile un accoppiamento libero tra i componenti runtime e le controparti in fase di progettazione e la possibilità di modificare i componenti della fase di progettazione senza incidere sul runtime. In questo esempio viene illustrato come programmare in base all'archivio di metadati applicando attributi a un tipo in fase di esecuzione, ovvero l'origine che non può essere controllata. Secondo la terminologia usata in genere, un'applicazione host registra i metadati per un set di tipi.  
  
 All'interno dell'output, è possibile notare un attributo aggiuntivo imprevisto, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`. Viene aggiunto in caso di utilizzo dell'API dei metadati e non ha alcun impatto sull'esecuzione dell'esempio.  
  
 In questo esempio viene illustrato quanto segue:  
  
## <a name="demonstrates"></a>Dimostrazione  
  
-   Inserimento di attributi tramite l'API dell'archivio di metadati.  
  
-   Uso di un meccanismo di callback per rinviare la registrazione di metadati.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ProgrammingMetadataStore.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`