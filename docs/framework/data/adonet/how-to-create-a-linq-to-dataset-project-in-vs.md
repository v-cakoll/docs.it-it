---
title: 'Procedura: creare un progetto LINQ to DataSet in Visual Studio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49ba6cb0-cdd2-4571-aeaa-25bf0f40e9b3
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c749cdd56f0c964b84788b05470406234ef3eb0a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-linq-to-dataset-project-in-visual-studio"></a>Procedura: creare un progetto LINQ to DataSet in Visual Studio
I tipi diversi di progetti [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] richiedono determinati spazi dei nomi importati (Visual Basic) o direttive `using` (C#) e riferimenti. Il requisito minimo è un riferimento a System.Core.dll e una direttiva `using` per <xref:System.Linq>. Per impostazione predefinita, questi elementi vengono forniti se si crea un nuovo progetto di [!INCLUDE[csharp_orcas_long](../../../../includes/csharp-orcas-long-md.md)]. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] richiede anche un riferimento a System.Data.dll e System.Data.DataSetExtensions.dll e una direttiva `Imports` (Visual Basic) o `using` (C#).  
  
 Se un progetto viene aggiornato da una versione precedente di Visual Studio, può essere necessario specificare manualmente questi riferimenti correlati a LINQ. Può inoltre essere necessario impostare manualmente il progetto in modo che sia destinato a .NET Framework versione 3.5.  
  
> [!NOTE]
>  Se si sta compilando da un prompt dei comandi, è necessario fare manualmente riferimento DLL correlate a LINQ in `drive` **:**\Programmi\Reference Assemblies\Microsoft\Framework\v3.5.  
  
### <a name="to-target-the-net-framework-35"></a>Per impostare .NET Framework 3.5 come destinazione  
  
1.  In [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] creare un nuovo progetto di Visual Basic o C#. In alternativa, è possibile aprire un progetto di Visual Basic o C# creato in Visual Studio 2005 e seguire le istruzioni per convertirlo in un progetto di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Per un progetto c#, fare clic su di **progetto** menu e quindi fare clic su **proprietà**.  
  
    1.  Nel **applicazione** selezionare .NET Framework 3.5 nella pagina delle proprietà di **Framework di destinazione** elenco a discesa.  
  
3.  Per un progetto di Visual Basic, scegliere il **progetto** menu e quindi fare clic su **proprietà**.  
  
    1.  Nel **compilare** pagina delle proprietà, fare clic su **opzioni di compilazione avanzate** e quindi selezionare .NET Framework 3.5 nel **il Framework di destinazione (tutte le configurazioni)** elenco a discesa.  
  
4.  Nel **progetto** menu, fare clic su **Aggiungi riferimento**, fare clic sul **.NET** scheda, scorrere verso il basso **core**, selezionarlo e quindi fare clic su  **OK**.  
  
5.  Aggiungere una direttiva `using` o uno spazio dei nomi importato per <xref:System.Linq> al progetto o al file del codice sorgente.  
  
     Per ulteriori informazioni, vedere [direttiva using](~/docs/csharp/language-reference/keywords/using-directive.md) o [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
### <a name="to-enable-linq-to-dataset-functionality"></a>Per abilitare la funzionalità LINQ to DataSet  
  
1.  Se necessario, seguire i passaggi illustrati precedentemente in questo argomento per aggiungere un riferimento a System.Core.dll e una direttiva `using` o uno spazio dei nomi importato per System.Linq.  
  
2.  In c# o Visual Basic, scegliere il **progetto** menu e quindi fare clic su **Aggiungi riferimento**.  
  
3.  Nel **Aggiungi riferimento** la finestra di dialogo, fare clic sul **.NET** scheda se non è in primo piano. Scorrere verso il basso **System. Data** e **DataSetExtensions** e fare clic su di essi. Fare clic su di **OK** pulsante.  
  
4.  Aggiungere una direttiva `using` o uno spazio dei nomi importato per <xref:System.Data> al progetto o al file del codice sorgente. Per ulteriori informazioni, vedere [direttiva using](~/docs/csharp/language-reference/keywords/using-directive.md) o [procedura: aggiungere o rimuovere spazi dei nomi importati (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
5.  Aggiungere un riferimento a System.Data.DataSetExtensions.dll per la funzionalità LINQ to DataSet. Aggiungere un riferimento a System.Data.dll, se non è già presente.  
  
6.  Facoltativamente, aggiungere una direttiva `using` o uno spazio dei nomi importato per `System.Data.Common` o `System.Data.SqlClient`, a seconda della modalità di connessione al database.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
 [Nozioni di base su LINQ](http://msdn.microsoft.com/library/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9)
