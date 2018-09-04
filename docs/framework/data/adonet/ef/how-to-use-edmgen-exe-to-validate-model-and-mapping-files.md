---
title: 'Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: fda8698381e98c64318f1a26f77f0263e9085074
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512445"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a><span data-ttu-id="2a6b7-102">Procedura: utilizzare EdmGen.exe per convalidare file di modello e di mapping</span><span class="sxs-lookup"><span data-stu-id="2a6b7-102">How to: Use EdmGen.exe to Validate Model and Mapping Files</span></span>
<span data-ttu-id="2a6b7-103">Questo argomento viene illustrato come usare il [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) dello strumento per convalidare il modello e i file di mapping.</span><span class="sxs-lookup"><span data-stu-id="2a6b7-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to validate the model and mapping files.</span></span> <span data-ttu-id="2a6b7-104">Per altre informazioni, vedere [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="2a6b7-104">For more information, see [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).</span></span>  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a><span data-ttu-id="2a6b7-105">Per convalidare il modello School usando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="2a6b7-105">To validate the School model using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="2a6b7-106">Creare il database School.</span><span class="sxs-lookup"><span data-stu-id="2a6b7-106">Create the School database.</span></span> <span data-ttu-id="2a6b7-107">Per altre informazioni, vedere [creazione del Database di esempio School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="2a6b7-107">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="2a6b7-108">Generare il modello School.</span><span class="sxs-lookup"><span data-stu-id="2a6b7-108">Generate the School model.</span></span> <span data-ttu-id="2a6b7-109">Per altre informazioni, vedere [procedura: usare EdmGen.exe per generare il file di modello e di Mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="2a6b7-109">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="2a6b7-110">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="2a6b7-110">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2a6b7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a6b7-111">See Also</span></span>  
 [<span data-ttu-id="2a6b7-112">Procedura: configurare manualmente un progetto Entity Framework</span><span class="sxs-lookup"><span data-stu-id="2a6b7-112">How to: Manually Configure an Entity Framework Project</span></span>](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="2a6b7-113">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="2a6b7-113">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="2a6b7-114">Procedura: pre-generare viste per migliorare le prestazioni delle Query</span><span class="sxs-lookup"><span data-stu-id="2a6b7-114">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="2a6b7-115">Procedura: Usare EdmGen.exe per generare codice a livello oggetti</span><span class="sxs-lookup"><span data-stu-id="2a6b7-115">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
