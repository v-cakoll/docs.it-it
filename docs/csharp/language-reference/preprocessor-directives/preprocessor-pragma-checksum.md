---
title: '#pragma checksum (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 28a9ccfb9d36e648304a177294904ab1b7f18892
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48024545"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="a0a22-102">#pragma checksum (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a0a22-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="a0a22-103">Consente di generare i checksum per i file di origine facilitando in tal modo le operazioni di debug delle pagine [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0a22-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0a22-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0a22-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0a22-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="a0a22-106">Nome del file che richiede il monitoraggio per modifiche o aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a0a22-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="a0a22-107">Identificatore univoco globale (GUID, Globally Unique Identifier) dell'algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="a0a22-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="a0a22-108">Stringa di cifre esadecimali che rappresenta i byte del checksum.</span><span class="sxs-lookup"><span data-stu-id="a0a22-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="a0a22-109">Deve essere un numero pari di cifre esadecimali.</span><span class="sxs-lookup"><span data-stu-id="a0a22-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="a0a22-110">Un numero dispari di cifre genera un avviso in fase di compilazione, pertanto la direttiva viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="a0a22-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0a22-111">Note</span><span class="sxs-lookup"><span data-stu-id="a0a22-111">Remarks</span></span>  
 <span data-ttu-id="a0a22-112">Il debugger di Visual Studio usa un checksum per trovare sempre l'origine corretta.</span><span class="sxs-lookup"><span data-stu-id="a0a22-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="a0a22-113">Il compilatore calcola il checksum di un file di origine, quindi genera l'output nel file del database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="a0a22-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="a0a22-114">Il PDB viene quindi usato dal debugger per eseguire il confronto con il checksum calcolato per il file di origine.</span><span class="sxs-lookup"><span data-stu-id="a0a22-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="a0a22-115">Questa soluzione non funziona per i progetti [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] ASP.NET, poiché il checksum calcolato si riferisce al file di origine generato piuttosto che al file ASPX.</span><span class="sxs-lookup"><span data-stu-id="a0a22-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="a0a22-116">Per risolvere questo problema, `#pragma checksum` fornisce supporto per il checksum nelle pagine [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0a22-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="a0a22-117">Quando si crea un progetto [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] in Visual C#, il file di origine generato contiene un checksum per il file ASPX, dal quale viene generata l'origine.</span><span class="sxs-lookup"><span data-stu-id="a0a22-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="a0a22-118">Queste informazioni vengono quindi scritte dal compilatore nel file PDB.</span><span class="sxs-lookup"><span data-stu-id="a0a22-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="a0a22-119">Se il compilatore non rileva alcuna direttiva `#pragma checksum` nel file, calcola il checksum e scrive il valore nel file PDB.</span><span class="sxs-lookup"><span data-stu-id="a0a22-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0a22-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="a0a22-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0a22-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0a22-121">See Also</span></span>

- [<span data-ttu-id="a0a22-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a0a22-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a0a22-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a0a22-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a0a22-124">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="a0a22-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
