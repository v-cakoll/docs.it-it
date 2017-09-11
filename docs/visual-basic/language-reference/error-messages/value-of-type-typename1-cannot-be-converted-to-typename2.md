---
title: "Valore di tipo &quot;&lt;NomeTipo1&gt;&quot;non può essere convertito in&quot;&lt;in NomeTipo2&gt;&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2fbe1550515d2b15a3e349392fc8d78812787ae4
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="28442-102">Valore di tipo '&lt;NomeTipo1&gt;'non può essere convertito in'&lt;in NomeTipo2&gt;'</span><span class="sxs-lookup"><span data-stu-id="28442-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="28442-103">Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'.</span><span class="sxs-lookup"><span data-stu-id="28442-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="28442-104">Mancata corrispondenza del tipo potrebbe essere dovuto all'unione di un riferimento al file con un riferimento progetto all'assembly '\<assemblyname >'.</span><span class="sxs-lookup"><span data-stu-id="28442-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="28442-105">Provare a sostituire il riferimento al file '\<filepath >' nel progetto '\<projectname1 >' con un riferimento al progetto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="28442-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="28442-106">In una situazione in cui un progetto contiene sia un riferimento al progetto un riferimento al file, il compilatore non garantisce che un tipo può essere convertito in un altro.</span><span class="sxs-lookup"><span data-stu-id="28442-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="28442-107">Il pseudo-codice seguente viene illustrata una situazione che può generare l'errore.</span><span class="sxs-lookup"><span data-stu-id="28442-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
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
  
 <span data-ttu-id="28442-108">Progetto `P1` rende un riferimento di progetto progetto indiretto `P2` al progetto `P3`e anche un riferimento al file diretto `P3`.</span><span class="sxs-lookup"><span data-stu-id="28442-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="28442-109">La dichiarazione di `commonObject` utilizza il riferimento al file `P3`, mentre la chiamata a `P2.getCommonClass` utilizza il riferimento al progetto `P3`.</span><span class="sxs-lookup"><span data-stu-id="28442-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="28442-110">Il problema in questa situazione è che il riferimento al file specifica un percorso e il nome del file di output di `P3` (in genere P3), mentre i riferimenti al progetto identificano il progetto di origine (`P3`) in base al nome di progetto.</span><span class="sxs-lookup"><span data-stu-id="28442-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="28442-111">Per questo motivo, il compilatore non garantisce che il tipo `P3.commonClass` proviene dallo stesso codice di origine tramite i due diversi riferimenti.</span><span class="sxs-lookup"><span data-stu-id="28442-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="28442-112">Questa situazione si verifica in genere quando i riferimenti di progetto e i riferimenti ai file vengono combinati.</span><span class="sxs-lookup"><span data-stu-id="28442-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="28442-113">Nell'illustrazione precedente, il problema non si verificherà se `P1` effettuato un riferimento diretto `P3` anziché un riferimento al file.</span><span class="sxs-lookup"><span data-stu-id="28442-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="28442-114">**ID errore:** BC30955</span><span class="sxs-lookup"><span data-stu-id="28442-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="28442-115">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="28442-115">To correct this error</span></span>  
  
-   <span data-ttu-id="28442-116">Modificare il riferimento al file a un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="28442-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28442-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28442-117">See Also</span></span>  
 <span data-ttu-id="28442-118">[Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="28442-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="28442-119"> [Gestione dei riferimenti in un progetto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="28442-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="28442-120"> [Procedura: aggiungere o rimuovere riferimenti utilizzando la finestra di dialogo Aggiungi riferimento](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="28442-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
