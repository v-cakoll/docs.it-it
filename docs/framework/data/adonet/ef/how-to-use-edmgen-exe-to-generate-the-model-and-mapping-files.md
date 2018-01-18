---
title: 'Procedura: utilizzare EdmGen.exe per generare i file di modello e di mapping'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5ffdd5e8ba8b4b0d46ac3165ed401179ff6bf630
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Procedura: utilizzare EdmGen.exe per generare i file di modello e di mapping
In questo argomento viene illustrato come usare lo strumento Generatore EDM (EdmGen.exe) per generare i seguenti file in base al database School:  
  
-   Modello concettuale (file con estensione csdl).  
  
-   Modello di archiviazione (file con estensione ssdl).  
  
-   Mapping tra i modelli concettuali e di archiviazione (file con estensione msl).  
  
-   Codice del livello oggetti in Visual Basic o C#.  
  
-   File di visualizzazione.  
  
 Lo strumento EdmGen.exe usa /mode:FullGeneration per la generazione dei file elencati in precedenza. Per ulteriori informazioni sui comandi EdmGen.exe, vedere [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Se si usa EdmGen.exe per generare i file di modello e di mapping, sarà comunque necessario configurare il progetto di [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] per l'uso di [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Per ulteriori informazioni, vedere [procedura: configurare manualmente un progetto Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Un modello concettuale generato da EdmGen.exe include tutti gli oggetti del database. Per generare un modello concettuale che include solo oggetti specifici, usare la Procedura guidata Entity Data Model. Per ulteriori informazioni, vedere [procedura: utilizzare la procedura guidata Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Per generare il modello School per un progetto Visual Basic usando EdmGen.exe  
  
1.  Creare il database School. Per ulteriori informazioni, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Per generare il modello School per un progetto C# usando EdmGen.exe  
  
1.  Creare il database School. Per ulteriori informazioni, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Modellazione e mapping](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Procedura: configurare manualmente un progetto Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Procedura: generare in anticipo visualizzazioni per migliorare le prestazioni delle Query](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Strumenti di ADO.NET Entity Data Model](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [Procedura: Usare EdmGen.exe per convalidare file di modello e di mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
