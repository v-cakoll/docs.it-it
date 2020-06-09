---
title: Esempio di UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: fb956882ae653f584026fefb20e261c90010ca9b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591059"
---
# <a name="uritemplate-sample"></a>Esempio di UriTemplate
La classe <xref:System.UriTemplate> fornisce metodi per l'utilizzo di set di URI che condividono una struttura comune. In questo esempio vengono illustrati i seguenti concetti principali relativi a `UriTemplate`:  
  
- Sintassi per la creazione di modelli.  
  
- Creazione di istanze degli URI da un `UriTemplate` utilizzando <xref:System.UriTemplate.BindByName%2A> e <xref:System.UriTemplate.BindByPosition%2A>.  
  
- <xref:System.UriTemplateTable.Match%2A>, che corrisponde all'operazione inversa di `BindByName` e `BindByPosition`.  
  
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
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a>Vedere anche

- [Tabella UriTemplate](uritemplate-table-sample.md)
- [Dispatcher della tabella UriTemplate](uritemplate-table-dispatcher-sample.md)
