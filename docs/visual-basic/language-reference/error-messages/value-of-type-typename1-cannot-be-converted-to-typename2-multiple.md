---
title: Valore di tipo &#39; &lt;NomeTipo1&gt; &#39; non può essere convertito in &#39; &lt;in NomeTipo2&gt; &#39; (più riferimenti di file)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 943b9612a9217b90c19f34285e812c4e1cccf81a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691373"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="7bdf4-102">Valore di tipo &#39; &lt;NomeTipo1&gt; &#39; non può essere convertito in &#39; &lt;in NomeTipo2&gt; &#39; (più riferimenti di file)</span><span class="sxs-lookup"><span data-stu-id="7bdf4-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="7bdf4-103">Valore di tipo '\<NomeTipo1 >' non può essere convertito in '\<in NomeTipo2 >'.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="7bdf4-104">Mancata corrispondenza del tipo potrebbe essere dovuto a un riferimento file a '\<filepath1 >' nel progetto '\<projectname1 >' con un riferimento file a '\<filepath2 >' nel progetto '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="7bdf4-105">Se gli assembly sono identici, provare a definire lo stesso percorso per entrambi i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="7bdf4-106">In una situazione in cui un progetto contiene più di un riferimento file a un assembly, il compilatore non può garantire che un tipo può essere convertito in un altro.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="7bdf4-107">Ogni riferimento di file specifica un percorso e nome file del file di output di un progetto (in genere un file DLL).</span><span class="sxs-lookup"><span data-stu-id="7bdf4-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="7bdf4-108">Il compilatore non può garantire che i file di output forniti dall'origine stessa, né che rappresentano la stessa versione dello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="7bdf4-109">Pertanto, non può garantire che i tipi i riferimenti sono dello stesso tipo, o può essere convertito anche che uno a altro.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="7bdf4-110">Se si sa che gli assembly di riferimento hanno la stessa identità di assembly, è possibile utilizzare un riferimento a file singolo.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="7bdf4-111">L' *identità dell'assembly* include il nome, la versione, la chiave pubblica e le eventuali impostazioni cultura dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="7bdf4-112">Queste informazioni identificano l'assembly in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="7bdf4-113">**ID errore:** BC30961</span><span class="sxs-lookup"><span data-stu-id="7bdf4-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7bdf4-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7bdf4-114">To correct this error</span></span>  
  
-   <span data-ttu-id="7bdf4-115">Se gli assembly di riferimento hanno la stessa identità di assembly, quindi rimuovere o sostituire uno dei riferimenti ai file in modo che sia presente solo un riferimento a file singolo.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="7bdf4-116">Se gli assembly di riferimento non è la stessa identità di assembly, quindi modificare il codice in modo che non prova a convertire un tipo in uno a un tipo in altro.</span><span class="sxs-lookup"><span data-stu-id="7bdf4-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bdf4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bdf4-117">See also</span></span>
- [<span data-ttu-id="7bdf4-118">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bdf4-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="7bdf4-119">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="7bdf4-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

