---
title: 'Procedura: utilizzare EdmGen.exe per generare codice a livello oggetti'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: cd919f382096af6ff3e5e27225619767f3922ff0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761090"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="471e6-102">Procedura: utilizzare EdmGen.exe per generare codice a livello oggetti</span><span class="sxs-lookup"><span data-stu-id="471e6-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="471e6-103">In questo argomento viene illustrato come utilizzare il [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) strumento per generare codice del livello oggetti in base al file con estensione CSDL.</span><span class="sxs-lookup"><span data-stu-id="471e6-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="471e6-104">Per generare il codice del livello oggetti per il modello School per un progetto di Visual Basic usando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="471e6-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="471e6-105">Creare il database School.</span><span class="sxs-lookup"><span data-stu-id="471e6-105">Create the School database.</span></span> <span data-ttu-id="471e6-106">Per ulteriori informazioni, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="471e6-106">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="471e6-107">Generare il modello School o ottenere il file School.csdl.</span><span class="sxs-lookup"><span data-stu-id="471e6-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="471e6-108">Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="471e6-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="471e6-109">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="471e6-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="471e6-110">Per generare il codice del livello oggetti per il modello School per un progetto di C# usando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="471e6-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="471e6-111">Creare il database School.</span><span class="sxs-lookup"><span data-stu-id="471e6-111">Create the School database.</span></span> <span data-ttu-id="471e6-112">Per ulteriori informazioni, vedere [la creazione di Database di esempio School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span><span class="sxs-lookup"><span data-stu-id="471e6-112">For more information, see [Creating the School Sample Database](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="471e6-113">Generare il modello School o ottenere il file School.csdl.</span><span class="sxs-lookup"><span data-stu-id="471e6-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="471e6-114">Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="471e6-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="471e6-115">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="471e6-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="471e6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="471e6-116">See Also</span></span>  
 [<span data-ttu-id="471e6-117">Modellazione e mapping</span><span class="sxs-lookup"><span data-stu-id="471e6-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [<span data-ttu-id="471e6-118">Procedura: configurare manualmente un progetto Entity Framework</span><span class="sxs-lookup"><span data-stu-id="471e6-118">How to: Manually Configure an Entity Framework Project</span></span>](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [<span data-ttu-id="471e6-119">Strumenti di ADO.NET Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="471e6-119">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="471e6-120">Procedura: generare in anticipo visualizzazioni per migliorare le prestazioni delle Query</span><span class="sxs-lookup"><span data-stu-id="471e6-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [<span data-ttu-id="471e6-121">Procedura: Usare EdmGen.exe per generare i file di modello e di mapping</span><span class="sxs-lookup"><span data-stu-id="471e6-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
