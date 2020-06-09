---
title: Tabella di esempio UriTemplate
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: ff88bdfe0c8c32da6f07f2b22de54af437376c51
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596435"
---
# <a name="uritemplate-table-sample"></a>Tabella di esempio UriTemplate
La classe <xref:System.UriTemplateTable> fornisce una struttura con tabella associativa simile a un dizionario per lavorare con un set di istanze `UriTemplate`. URI (Uniform Resource Identifier) specifici possono essere associati in modo efficace con tutti i modelli della tabella e i dati associati al modello corrispondente possono essere recuperati.  
  
 In questo esempio vengono illustrati i seguenti concetti principali relativi alla classe `UriTemplateTable`:  
  
- Sintassi per la creazione di un'istanza `UriTemplateTable`.  
  
- Popolare una `UriTemplateTable` con un set di coppie chiave/valore.  
  
- Associare un candidato URI alla tabella utilizzando <xref:System.UriTemplateTable.MatchSingle%2A>.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
2. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a>Vedere anche

- [Dispatcher della tabella UriTemplate](uritemplate-table-dispatcher-sample.md)
- [UriTemplate](uritemplate-sample.md)
