---
title: '#pragma checksum (Riferimenti per C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0604a559be25c300fcdc6041975306b465fc595f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="c8f52-102">#pragma checksum (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c8f52-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="c8f52-103">Consente di generare i checksum per i file di origine facilitando in tal modo le operazioni di debug delle pagine [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8f52-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8f52-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8f52-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8f52-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="c8f52-106">Nome del file che richiede il monitoraggio per modifiche o aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="c8f52-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="c8f52-107">Identificatore univoco globale (GUID, Globally Unique Identifier) del file.</span><span class="sxs-lookup"><span data-stu-id="c8f52-107">The Globally Unique Identifier (GUID) for the file.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="c8f52-108">Stringa di cifre esadecimali che rappresenta i byte del checksum.</span><span class="sxs-lookup"><span data-stu-id="c8f52-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="c8f52-109">Deve essere un numero pari di cifre esadecimali.</span><span class="sxs-lookup"><span data-stu-id="c8f52-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="c8f52-110">Un numero dispari di cifre genera un avviso in fase di compilazione, pertanto la direttiva viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="c8f52-110">An odd number of digits results in a compile-time warning, and the directive are  ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8f52-111">Note</span><span class="sxs-lookup"><span data-stu-id="c8f52-111">Remarks</span></span>  
 <span data-ttu-id="c8f52-112">Il debugger di Visual Studio usa un checksum per trovare sempre l'origine corretta.</span><span class="sxs-lookup"><span data-stu-id="c8f52-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="c8f52-113">Il compilatore calcola il checksum di un file di origine, quindi genera l'output nel file del database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="c8f52-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="c8f52-114">Il PDB viene quindi usato dal debugger per eseguire il confronto con il checksum calcolato per il file di origine.</span><span class="sxs-lookup"><span data-stu-id="c8f52-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="c8f52-115">Questa soluzione non funziona per i progetti [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] ASP.NET, poiché il checksum calcolato si riferisce al file di origine generato piuttosto che al file ASPX.</span><span class="sxs-lookup"><span data-stu-id="c8f52-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="c8f52-116">Per risolvere questo problema, `#pragma checksum` fornisce supporto per il checksum nelle pagine [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8f52-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="c8f52-117">Quando si crea un progetto [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] in [!INCLUDE[csprcs](~/includes/csprcs-md.md)], il file di origine generato contiene un checksum per il file ASPX, dal quale viene generata l'origine.</span><span class="sxs-lookup"><span data-stu-id="c8f52-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in [!INCLUDE[csprcs](~/includes/csprcs-md.md)], the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="c8f52-118">Queste informazioni vengono quindi scritte dal compilatore nel file PDB.</span><span class="sxs-lookup"><span data-stu-id="c8f52-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="c8f52-119">Se il compilatore non rileva alcuna direttiva `#pragma checksum` nel file, calcola il checksum e scrive il valore nel file PDB.</span><span class="sxs-lookup"><span data-stu-id="c8f52-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8f52-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8f52-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8f52-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8f52-121">See Also</span></span>  
 [<span data-ttu-id="c8f52-122">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="c8f52-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c8f52-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c8f52-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c8f52-124">Direttive per il preprocessore C#</span><span class="sxs-lookup"><span data-stu-id="c8f52-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
