---
title: <message> Questo errore potrebbe essere dovuto anche all'unione di un riferimento file con un riferimento progetto nell'assembly '<assemblyname>'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 263e30f992ef58b0053acb2fd749d0d9186ef6b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397259"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="a951f-102">\<message> Questo errore potrebbe essere dovuto anche all'unione di un riferimento file con un riferimento progetto nell'assembly '\<assemblyname>'</span><span class="sxs-lookup"><span data-stu-id="a951f-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>
<span data-ttu-id="a951f-103">\<message>Questo errore può essere dovuto anche alla combinazione di un riferimento di file con un riferimento di progetto all'assembly \<assemblyname> .</span><span class="sxs-lookup"><span data-stu-id="a951f-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="a951f-104">In questo caso, provare a sostituire il riferimento file \<assemblyfilename> con '' nel progetto ' \<projectname1> ' con un riferimento al progetto a' \<projectname2> '.</span><span class="sxs-lookup"><span data-stu-id="a951f-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="a951f-105">Il codice del progetto accede a un membro di un altro progetto, ma la configurazione della soluzione non consente al compilatore Visual Basic di risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="a951f-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="a951f-106">Per accedere a un tipo definito in un altro assembly, il compilatore Visual Basic deve avere un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="a951f-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="a951f-107">Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.</span><span class="sxs-lookup"><span data-stu-id="a951f-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="a951f-108">**ID errore:** BC30971</span><span class="sxs-lookup"><span data-stu-id="a951f-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a951f-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a951f-109">To correct this error</span></span>  
  
1. <span data-ttu-id="a951f-110">Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="a951f-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="a951f-111">Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="a951f-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="a951f-112">Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="a951f-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a951f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a951f-113">See also</span></span>

- [<span data-ttu-id="a951f-114">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="a951f-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="a951f-115">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a951f-115">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="a951f-116">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="a951f-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="a951f-117">Risoluzione dei problemi relativi ai riferimenti interrotti</span><span class="sxs-lookup"><span data-stu-id="a951f-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
