---
title: 'Procedura: Usare EdmGen.exe per generare codice del livello oggetti'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 4acc60f324d41ed23ad3ef63907b031f003b07c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827159"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="960c5-102">Procedura: Usare EdmGen.exe per generare codice del livello oggetti</span><span class="sxs-lookup"><span data-stu-id="960c5-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="960c5-103">Questo argomento viene illustrato come usare il [generatore EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) strumento per generare codice del livello oggetti in base al file CSDL.</span><span class="sxs-lookup"><span data-stu-id="960c5-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="960c5-104">Per generare il codice del livello oggetti per il modello School per un progetto di Visual Basic usando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="960c5-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="960c5-105">Creare il database School.</span><span class="sxs-lookup"><span data-stu-id="960c5-105">Create the School database.</span></span> <span data-ttu-id="960c5-106">Per altre informazioni, vedere [creazione del Database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="960c5-106">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="960c5-107">Generare il modello School o ottenere il file School.csdl.</span><span class="sxs-lookup"><span data-stu-id="960c5-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="960c5-108">Per altre informazioni, vedere [Procedura: Consente di generare il modello e i file di Mapping EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="960c5-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="960c5-109">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="960c5-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="960c5-110">Per generare il codice del livello oggetti per il modello School per un progetto di C# usando EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="960c5-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="960c5-111">Creare il database School.</span><span class="sxs-lookup"><span data-stu-id="960c5-111">Create the School database.</span></span> <span data-ttu-id="960c5-112">Per altre informazioni, vedere [creazione del Database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="960c5-112">For more information, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="960c5-113">Generare il modello School o ottenere il file School.csdl.</span><span class="sxs-lookup"><span data-stu-id="960c5-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="960c5-114">Per altre informazioni, vedere [Procedura: Consente di generare il modello e i file di Mapping EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="960c5-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="960c5-115">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="960c5-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="960c5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="960c5-116">See also</span></span>
- [<span data-ttu-id="960c5-117">Modellazione e mapping</span><span class="sxs-lookup"><span data-stu-id="960c5-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- <span data-ttu-id="960c5-118">[Procedura: Configurare manualmente un progetto Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="960c5-118">[How to: Manually Configure an Entity Framework Project](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="960c5-119">[Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="960c5-119">[ADO.NET Entity Data Model  Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="960c5-120">[Procedura: Pre-generare viste per migliorare le prestazioni delle Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="960c5-120">[How to: Pre-Generate Views to Improve Query Performance](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="960c5-121">Procedura: Usare EdmGen.exe per generare il modello e i file di Mapping</span><span class="sxs-lookup"><span data-stu-id="960c5-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
