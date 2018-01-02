---
title: 'Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2a8bf70468bc2daec054acad577fa4c216cb25e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="c56d3-102">Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping</span><span class="sxs-lookup"><span data-stu-id="c56d3-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="c56d3-103">In questo argomento viene illustrato come utilizzare il [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) strumento per convalidare il modello e i file di mapping.</span><span class="sxs-lookup"><span data-stu-id="c56d3-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="c56d3-104">Per ulteriori informazioni, vedere [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="c56d3-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="c56d3-105">Per convalidare il modello School usando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="c56d3-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="c56d3-106">Creare il database School.</span><span class="sxs-lookup"><span data-stu-id="c56d3-106">Create the School database.</span></span> <span data-ttu-id="c56d3-107">Per ulteriori informazioni, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="c56d3-107">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="c56d3-108">Generare il modello School.</span><span class="sxs-lookup"><span data-stu-id="c56d3-108">Generate the School model.</span></span> <span data-ttu-id="c56d3-109">Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="c56d3-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="c56d3-110">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="c56d3-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c56d3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c56d3-111">See Also</span></span>  
 [<span data-ttu-id="c56d3-112">Procedura: configurare manualmente un progetto Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c56d3-112">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="c56d3-113">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="c56d3-113">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="c56d3-114">Procedura: generare in anticipo visualizzazioni per migliorare le prestazioni delle Query</span><span class="sxs-lookup"><span data-stu-id="c56d3-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/en-us/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="c56d3-115">Procedura: Usare EdmGen.exe per generare codice a livello oggetti</span><span class="sxs-lookup"><span data-stu-id="c56d3-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
