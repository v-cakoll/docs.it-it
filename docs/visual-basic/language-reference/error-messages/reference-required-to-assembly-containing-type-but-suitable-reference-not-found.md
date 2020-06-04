---
title: Necessario riferimento all'assembly '<assemblyidentity>' contenente il tipo '<typename>'. Impossibile trovare un riferimento adatto a causa dell'ambiguità tra i progetti '<projectname1>' e '<projectname2>'
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 4b9f74f0627268752b0ba3c3816fe9d4cc8a231b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404823"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="406d4-102">Necessario riferimento all'assembly '\<assemblyidentity>' contenente il tipo '\<typename>'. Impossibile trovare un riferimento adatto a causa dell'ambiguità tra i progetti '\<projectname1>' e '\<projectname2>'</span><span class="sxs-lookup"><span data-stu-id="406d4-102">Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>
<span data-ttu-id="406d4-103">In un'espressione viene usato un tipo, ad esempio una classe, una struttura, un'interfaccia, un'enumerazione o un delegato, definito all'esterno del progetto.</span><span class="sxs-lookup"><span data-stu-id="406d4-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="406d4-104">Tuttavia, sono presenti riferimenti di progetto a più assembly che definiscono quel tipo.</span><span class="sxs-lookup"><span data-stu-id="406d4-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="406d4-105">I progetti citati generano assembly con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="406d4-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="406d4-106">Pertanto, il compilatore non può determinare l'assembly da usare per il tipo a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="406d4-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="406d4-107">Per accedere a un tipo definito in un altro assembly, il compilatore Visual Basic deve avere un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="406d4-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="406d4-108">Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.</span><span class="sxs-lookup"><span data-stu-id="406d4-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="406d4-109">**ID errore:** BC30969</span><span class="sxs-lookup"><span data-stu-id="406d4-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="406d4-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="406d4-110">To correct this error</span></span>  
  
1. <span data-ttu-id="406d4-111">Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="406d4-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="406d4-112">Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="406d4-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="406d4-113">Nelle proprietà del progetto aggiungere un riferimento al file contenente l'assembly che definisce il tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="406d4-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406d4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="406d4-114">See also</span></span>

- [<span data-ttu-id="406d4-115">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="406d4-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="406d4-116">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="406d4-116">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="406d4-117">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="406d4-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="406d4-118">Risoluzione dei problemi relativi ai riferimenti interrotti</span><span class="sxs-lookup"><span data-stu-id="406d4-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
