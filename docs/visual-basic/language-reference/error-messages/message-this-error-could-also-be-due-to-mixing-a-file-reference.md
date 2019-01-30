---
title: <message> L'errore potrebbe inoltre essere dovuto all'unione di un riferimento di file con un riferimento al progetto nell'assembly '<assemblyname>'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: f28327b4df5b15f368f736e7402179227035a06e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272552"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="69f6b-102">\<messaggio > Questo errore potrebbe inoltre essere dovuto all'unione di un riferimento al file con un riferimento progetto all'assembly '\<assemblyname >'</span><span class="sxs-lookup"><span data-stu-id="69f6b-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>
<span data-ttu-id="69f6b-103">\<messaggio > Questo errore potrebbe inoltre essere dovuto all'unione di un riferimento al file con un riferimento progetto all'assembly '\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="69f6b-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="69f6b-104">In questo caso, provare a sostituire il riferimento file a '\<assemblyfilename >' nel progetto '\<projectname1 >' con un riferimento al progetto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="69f6b-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="69f6b-105">Il codice del progetto accede a un membro di un altro progetto, ma la configurazione della soluzione non supporta il compilatore Visual Basic risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="69f6b-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="69f6b-106">Per accedere a un tipo definito in un altro assembly, il compilatore Visual Basic deve avere un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="69f6b-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="69f6b-107">Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.</span><span class="sxs-lookup"><span data-stu-id="69f6b-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="69f6b-108">**ID errore:** BC30971</span><span class="sxs-lookup"><span data-stu-id="69f6b-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69f6b-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="69f6b-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="69f6b-110">Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="69f6b-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="69f6b-111">Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="69f6b-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="69f6b-112">Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="69f6b-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69f6b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69f6b-113">See also</span></span>
- [<span data-ttu-id="69f6b-114">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="69f6b-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="69f6b-115">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="69f6b-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="69f6b-116">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="69f6b-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="69f6b-117">Risoluzione dei problemi relativi ai riferimenti interrotti</span><span class="sxs-lookup"><span data-stu-id="69f6b-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
