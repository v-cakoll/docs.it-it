---
title: "Valore di tipo &quot;&lt;NomeTipo1&gt;&quot;non può essere convertito in&quot;&lt;in NomeTipo2&gt;&quot; (più riferimenti a file) | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
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
ms.openlocfilehash: 299cc4bec00a4597a661c5da49135fe3b5357537
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="61fde-102">Valore di tipo '&lt;NomeTipo1&gt;'non può essere convertito in'&lt;in NomeTipo2&gt;' (più riferimenti a file)</span><span class="sxs-lookup"><span data-stu-id="61fde-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="61fde-103">Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'.</span><span class="sxs-lookup"><span data-stu-id="61fde-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="61fde-104">Mancata corrispondenza del tipo potrebbe essere dovuto all'unione di un riferimento al file '\<filepath1 >' nel progetto '\<projectname1 >' con un riferimento al file '\<filepath2 >' nel progetto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="61fde-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="61fde-105">Se gli assembly sono identici, provare a definire lo stesso percorso per entrambi i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="61fde-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="61fde-106">In una situazione in cui un progetto contiene più di un riferimento al file a un assembly, il compilatore non garantisce che un tipo può essere convertito in un altro.</span><span class="sxs-lookup"><span data-stu-id="61fde-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="61fde-107">Ogni riferimento a file specifica un percorso e il nome del file di output di un progetto (in genere un file DLL).</span><span class="sxs-lookup"><span data-stu-id="61fde-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="61fde-108">Il compilatore non garantisce che i file di output provengano dalla stessa origine o che rappresentano la stessa versione dello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="61fde-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="61fde-109">Pertanto non garantisce che i tipi di riferimenti diversi sono dello stesso tipo, o anche che una può essere convertita a altro.</span><span class="sxs-lookup"><span data-stu-id="61fde-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="61fde-110">Se si conosce che gli assembly di riferimento hanno la stessa identità di assembly, è possibile utilizzare un riferimento a file singolo.</span><span class="sxs-lookup"><span data-stu-id="61fde-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="61fde-111">L' *identità dell'assembly* include il nome, la versione, la chiave pubblica e le eventuali impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="61fde-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="61fde-112">Queste informazioni identificano l'assembly in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="61fde-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="61fde-113">**ID errore:** BC30961</span><span class="sxs-lookup"><span data-stu-id="61fde-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61fde-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="61fde-114">To correct this error</span></span>  
  
-   <span data-ttu-id="61fde-115">Se gli assembly di riferimento hanno la stessa identità di assembly, rimuovere o sostituire uno dei riferimenti di file in modo che sia presente solo un riferimento a file singolo.</span><span class="sxs-lookup"><span data-stu-id="61fde-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="61fde-116">Se gli assembly di riferimento non hanno la stessa identità dell'assembly, quindi modificare il codice in modo che non effettua il tentativo di convertire un tipo in uno a un tipo in altro.</span><span class="sxs-lookup"><span data-stu-id="61fde-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61fde-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61fde-117">See Also</span></span>  
 <span data-ttu-id="61fde-118">[Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="61fde-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="61fde-119"> [Gestione dei riferimenti in un progetto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="61fde-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="61fde-120"> [Procedura: aggiungere o rimuovere riferimenti utilizzando la finestra di dialogo Aggiungi riferimento](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="61fde-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
