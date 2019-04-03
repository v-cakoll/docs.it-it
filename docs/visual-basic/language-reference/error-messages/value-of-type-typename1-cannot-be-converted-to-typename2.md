---
title: Impossibile convertire il valore di tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829024"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="88ab1-102">Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'</span><span class="sxs-lookup"><span data-stu-id="88ab1-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="88ab1-103">Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'.</span><span class="sxs-lookup"><span data-stu-id="88ab1-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="88ab1-104">Mancata corrispondenza del tipo potrebbe essere dovuto a combinare un riferimento al file con un riferimento progetto all'assembly '\<assemblyname >'.</span><span class="sxs-lookup"><span data-stu-id="88ab1-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="88ab1-105">Provare a sostituire il riferimento file a '\<percorsofile >' nel progetto '\<projectname1 >' con un riferimento al progetto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="88ab1-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="88ab1-106">In una situazione in cui un progetto contiene sia un riferimento al progetto un riferimento al file, il compilatore non può garantire che un tipo può essere convertito in un altro.</span><span class="sxs-lookup"><span data-stu-id="88ab1-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="88ab1-107">Il pseudo-codice seguente illustra una situazione che può generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="88ab1-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="88ab1-108">Project `P1` contiene un riferimento indiretto progetti tramite project `P2` al progetto `P3`e anche un riferimento di file dirette a `P3`.</span><span class="sxs-lookup"><span data-stu-id="88ab1-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="88ab1-109">La dichiarazione di `commonObject` utilizza il riferimento al file per `P3`, mentre la chiamata a `P2.getCommonClass` utilizza il riferimento al progetto `P3`.</span><span class="sxs-lookup"><span data-stu-id="88ab1-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="88ab1-110">Il problema in questa situazione è che il riferimento al file specifica un percorso e nome file per file di output del `P3` (in genere P3), mentre i riferimenti al progetto identifica il progetto di origine (`P3`) in base al nome di progetto.</span><span class="sxs-lookup"><span data-stu-id="88ab1-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="88ab1-111">Per questo motivo, il compilatore non garantisce che il tipo `P3.commonClass` proviene lo stesso codice sorgente tramite i due diversi riferimenti.</span><span class="sxs-lookup"><span data-stu-id="88ab1-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="88ab1-112">Questa situazione si verifica in genere quando i riferimenti al progetto e riferimenti a file sono di tipo misto.</span><span class="sxs-lookup"><span data-stu-id="88ab1-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="88ab1-113">Nella figura precedente, il problema non si verificherà se `P1` reso un riferimento diretto a `P3` anziché un riferimento al file.</span><span class="sxs-lookup"><span data-stu-id="88ab1-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="88ab1-114">**ID errore:** BC30955</span><span class="sxs-lookup"><span data-stu-id="88ab1-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88ab1-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="88ab1-115">To correct this error</span></span>  
  
-   <span data-ttu-id="88ab1-116">Modificare il riferimento file a un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="88ab1-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ab1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88ab1-117">See also</span></span>

- [<span data-ttu-id="88ab1-118">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88ab1-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="88ab1-119">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="88ab1-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
