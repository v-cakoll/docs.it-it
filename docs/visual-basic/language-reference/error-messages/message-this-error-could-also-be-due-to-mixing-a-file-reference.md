---
title: '&lt;messaggio&gt; questo errore potrebbe anche essere dovuta alla combinazione di un riferimento a file e un riferimento progetto all''assembly &#39;&lt; AssemblyName&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="1f34c-102">&lt;messaggio&gt; questo errore potrebbe anche essere dovuta alla combinazione di un riferimento a file e un riferimento progetto all'assembly &#39;&lt; AssemblyName&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="1f34c-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="1f34c-103">\<messaggio > Questo errore potrebbe anche essere dovuta alla combinazione di un riferimento al file con un riferimento progetto all'assembly '\<NomeAssembly >.</span><span class="sxs-lookup"><span data-stu-id="1f34c-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="1f34c-104">In questo caso, provare a sostituire il riferimento file a '\<assemblyfilename >' nel progetto '\<nomeprogetto1 >' con un riferimento al progetto '\<nomeprogetto2 >'.</span><span class="sxs-lookup"><span data-stu-id="1f34c-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="1f34c-105">Il codice del progetto accede a un membro di un altro progetto, ma la configurazione della soluzione non permette al compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="1f34c-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="1f34c-106">Per accedere a un tipo definito in un altro assembly, il compilatore [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve avere un riferimento a quell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1f34c-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="1f34c-107">Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.</span><span class="sxs-lookup"><span data-stu-id="1f34c-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="1f34c-108">**ID errore:** BC30971</span><span class="sxs-lookup"><span data-stu-id="1f34c-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f34c-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1f34c-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="1f34c-110">Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="1f34c-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="1f34c-111">Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="1f34c-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="1f34c-112">Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="1f34c-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f34c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f34c-113">See Also</span></span>  
 [<span data-ttu-id="1f34c-114">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="1f34c-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="1f34c-115">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="1f34c-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="1f34c-116">NIB Procedura: Aggiungere o rimuovere riferimenti utilizzando la finestra di dialogo Aggiungi riferimento</span><span class="sxs-lookup"><span data-stu-id="1f34c-116">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="1f34c-117">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="1f34c-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="1f34c-118">Risoluzione dei problemi relativi ai riferimenti interrotti</span><span class="sxs-lookup"><span data-stu-id="1f34c-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
