---
title: Impossibile convertire il valore di tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: f6b35efbc445887c537b94dd299b317a28e5f689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406560"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="1aaaf-102">Impossibile convertire il valore di tipo '\<typename1>' in '\<typename2>'</span><span class="sxs-lookup"><span data-stu-id="1aaaf-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="1aaaf-103">Non è possibile convertire il valore di tipo ' \<typename1> ' in ' \<typename2> '.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="1aaaf-104">Il tipo non corrisponde potrebbe essere dovuto alla combinazione di un riferimento file con un riferimento di progetto all'assembly ' \<assemblyname> '.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="1aaaf-105">Provare a sostituire il riferimento file \<filepath> con '' nel progetto ' \<projectname1> ' con un riferimento di progetto a' \<projectname2> '.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="1aaaf-106">In una situazione in cui un progetto rende un riferimento al progetto e un file di riferimento, il compilatore non può garantire che un tipo possa essere convertito in un altro.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="1aaaf-107">Lo pseudo-codice seguente illustra una situazione in cui è possibile generare questo errore.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
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
  
 <span data-ttu-id="1aaaf-108">`P1`Il progetto esegue un riferimento indiretto al progetto tramite `P2` il progetto al progetto `P3` e anche un riferimento diretto a un file `P3` .</span><span class="sxs-lookup"><span data-stu-id="1aaaf-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="1aaaf-109">La dichiarazione di `commonObject` utilizza il riferimento al file `P3` , mentre la chiamata a `P2.getCommonClass` utilizza il riferimento del progetto a `P3` .</span><span class="sxs-lookup"><span data-stu-id="1aaaf-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="1aaaf-110">Il problema in questa situazione è che il riferimento al file specifica un percorso e un nome di file per il file di output di `P3` (in genere P3. dll), mentre i riferimenti al progetto identificano il progetto di origine ( `P3` ) in base al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="1aaaf-111">Per questo motivo, il compilatore non può garantire che il tipo `P3.commonClass` provenga dallo stesso codice sorgente attraverso i due riferimenti diversi.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="1aaaf-112">Questa situazione si verifica in genere quando i riferimenti al progetto e i riferimenti ai file sono misti.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="1aaaf-113">Nell'illustrazione precedente il problema non si verifica se è `P1` stato creato un riferimento diretto a un progetto `P3` anziché un riferimento a un file.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="1aaaf-114">**ID errore:** BC30955</span><span class="sxs-lookup"><span data-stu-id="1aaaf-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1aaaf-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1aaaf-115">To correct this error</span></span>  
  
- <span data-ttu-id="1aaaf-116">Modificare il riferimento al file in un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="1aaaf-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aaaf-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aaaf-117">See also</span></span>

- [<span data-ttu-id="1aaaf-118">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1aaaf-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="1aaaf-119">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="1aaaf-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
