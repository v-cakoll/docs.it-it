---
title: Caricare da XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: c46c9020f07731d3d833332d77fd46a162ccb6dc
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715958"
---
# <a name="load-from-xaml"></a>Caricare da XAML
In questo esempio viene illustrato come caricare dinamicamente un flusso di lavoro XAML senza dovere eseguire lo strumento XamlBuildTask. Nell'esempio viene chiamato il metodo <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>. L'esempio è un'applicazione client Windows Presentation Foundation (WPF) che carica i flussi di lavoro XAML usando la classe <xref:System.Activities.XamlIntegration.ActivityXamlServices> e li esegue. Dopo essere stati caricati usando la classe <xref:System.Activities.XamlIntegration.ActivityXamlServices>, viene restituito un oggetto <xref:System.Activities.DynamicActivity%601> che può essere eseguito.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2010 aprire il file della soluzione LoadFromXAML. sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere CTRL+F5.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
