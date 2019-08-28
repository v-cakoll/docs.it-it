---
title: Caricare da XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 2f45beb398e6d6b91bf7444dd590b862ff8c7515
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038091"
---
# <a name="load-from-xaml"></a>Caricare da XAML
In questo esempio viene illustrato come caricare dinamicamente un flusso di lavoro XAML senza dovere eseguire lo strumento XamlBuildTask. Nell'esempio viene chiamato il metodo <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>. L'esempio è un'applicazione client Windows Presentation Foundation (WPF) che carica i flussi di lavoro XAML <xref:System.Activities.XamlIntegration.ActivityXamlServices> usando la classe e li esegue. Dopo essere stati caricati usando la classe <xref:System.Activities.XamlIntegration.ActivityXamlServices>, viene restituito un oggetto <xref:System.Activities.DynamicActivity%601> che può essere eseguito.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2010 aprire il file della soluzione LoadFromXAML. sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere CTRL+F5.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
