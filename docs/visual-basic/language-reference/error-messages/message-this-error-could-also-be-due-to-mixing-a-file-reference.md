---
title: '&lt;messaggio&gt; questo errore potrebbe inoltre essere dovuto all&quot;unione di un riferimento al file con un riferimento progetto all&quot;assembly &quot;&lt;assemblyname&gt;&quot; | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
dev_langs:
- VB
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c0908b1a13b9b9c54fb533201404987e479c6138
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="ce2e7-102">&lt;messaggio&gt; questo errore potrebbe inoltre essere dovuto all'unione di un riferimento al file con un riferimento progetto all'assembly '&lt;assemblyname&gt;'</span><span class="sxs-lookup"><span data-stu-id="ce2e7-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="ce2e7-103">\<messaggio > questo errore potrebbe inoltre essere dovuto all'unione di un riferimento al file con un riferimento progetto all'assembly '\<assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="ce2e7-104">In questo caso, provare a sostituire il riferimento al file '\<assemblyfilename >' nel progetto '\<projectname1 >' con un riferimento al progetto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="ce2e7-105">Il codice del progetto accede a un membro di un altro progetto, ma non consente la configurazione della soluzione di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore per risolvere il riferimento.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="ce2e7-106">Accedere a un tipo definito in un altro assembly, il [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore deve avere un riferimento a tale assembly.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="ce2e7-107">Deve trattarsi di un riferimento unico, non ambiguo, che non generi riferimenti circolari tra i progetti.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="ce2e7-108">**ID errore:** BC30971</span><span class="sxs-lookup"><span data-stu-id="ce2e7-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce2e7-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ce2e7-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="ce2e7-110">Determinare quale progetto produce l'assembly migliore per il progetto a cui fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="ce2e7-111">Per questa decisione si potrebbero usare criteri quali la facilità di accesso al file e la frequenza di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="ce2e7-112">Nelle proprietà del progetto aggiungere un riferimento al progetto contenente l'assembly che definisce il tipo in uso.</span><span class="sxs-lookup"><span data-stu-id="ce2e7-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2e7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce2e7-113">See Also</span></span>  
 <span data-ttu-id="ce2e7-114">[Gestione dei riferimenti in un progetto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="ce2e7-114">[Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="ce2e7-115"> [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="ce2e7-115"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="ce2e7-116"> [NIB Procedura: Aggiungere o rimuovere riferimenti usando la finestra di dialogo Aggiungi riferimento](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="ce2e7-116"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="ce2e7-117"> [NIB procedura: modificare le proprietà del progetto e le impostazioni di configurazione](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="ce2e7-117"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="ce2e7-118"> [Risoluzione dei problemi relativi ai riferimenti interrotti](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="ce2e7-118"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
