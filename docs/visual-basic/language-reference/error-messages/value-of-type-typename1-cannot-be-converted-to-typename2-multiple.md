---
title: Impossibile convertire il valore del tipo '<typename1>' in '<typename2>'
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 25008f05979638e050b74fc659fdc0a6d13b3c31
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406586"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a><span data-ttu-id="3f2de-102">Impossibile convertire il valore del tipo '\<typename1>' in '\<typename2>'</span><span class="sxs-lookup"><span data-stu-id="3f2de-102">Value of type '\<typename1>' cannot be converted to '\<typename2>' (Multiple file references)</span></span>
<span data-ttu-id="3f2de-103">Non è possibile convertire il valore di tipo ' \<typename1> ' in ' \<typename2> '.</span><span class="sxs-lookup"><span data-stu-id="3f2de-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="3f2de-104">Il tipo non corrispondente potrebbe essere dovuto alla combinazione di un riferimento file a' \<filepath1> ' nel progetto ' \<projectname1> ' con un riferimento file a' \<filepath2> ' nel progetto ' \<projectname2> '.</span><span class="sxs-lookup"><span data-stu-id="3f2de-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="3f2de-105">Se gli assembly sono identici, provare a definire lo stesso percorso per entrambi i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="3f2de-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="3f2de-106">In una situazione in cui un progetto crea più di un riferimento di file a un assembly, il compilatore non può garantire che un tipo possa essere convertito in un altro.</span><span class="sxs-lookup"><span data-stu-id="3f2de-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="3f2de-107">Ogni riferimento a file specifica un percorso e un nome di file per il file di output di un progetto (in genere un file DLL).</span><span class="sxs-lookup"><span data-stu-id="3f2de-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="3f2de-108">Il compilatore non può garantire che i file di output provengano dalla stessa origine o che rappresentino la stessa versione dello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="3f2de-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="3f2de-109">Pertanto, non è in grado di garantire che i tipi nei diversi riferimenti siano dello stesso tipo o anche che uno possa essere convertito nell'altro.</span><span class="sxs-lookup"><span data-stu-id="3f2de-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="3f2de-110">È possibile utilizzare un singolo riferimento a file se si è certi che gli assembly a cui si fa riferimento hanno la stessa identità di assembly.</span><span class="sxs-lookup"><span data-stu-id="3f2de-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="3f2de-111">L' *identità dell'assembly* include il nome dell'assembly, la versione, la chiave pubblica, se presente, e le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="3f2de-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="3f2de-112">Queste informazioni identificano l'assembly in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="3f2de-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="3f2de-113">**ID errore:** BC30961</span><span class="sxs-lookup"><span data-stu-id="3f2de-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f2de-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3f2de-114">To correct this error</span></span>  
  
- <span data-ttu-id="3f2de-115">Se gli assembly a cui si fa riferimento hanno la stessa identità di assembly, rimuovere o sostituire uno dei riferimenti al file in modo che sia presente un solo riferimento a un file.</span><span class="sxs-lookup"><span data-stu-id="3f2de-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
- <span data-ttu-id="3f2de-116">Se gli assembly a cui si fa riferimento non hanno la stessa identità di assembly, modificare il codice in modo che non tenti di convertire un tipo in un tipo in un altro.</span><span class="sxs-lookup"><span data-stu-id="3f2de-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2de-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f2de-117">See also</span></span>

- [<span data-ttu-id="3f2de-118">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3f2de-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="3f2de-119">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="3f2de-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
