---
title: Tipo '<typename>' non definito
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 89e2d1d18b456c96f62d6b9ee1dd8dc9d41bf665
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386932"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="136eb-102">Tipo '\<typename>' non definito</span><span class="sxs-lookup"><span data-stu-id="136eb-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="136eb-103">L'istruzione ha fatto riferimento a un tipo che non è stato definito.</span><span class="sxs-lookup"><span data-stu-id="136eb-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="136eb-104">È possibile definire un tipo in un'istruzione di dichiarazione, ad esempio `Enum` ,, `Structure` `Class` o `Interface` .</span><span class="sxs-lookup"><span data-stu-id="136eb-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="136eb-105">**ID errore:** BC30002</span><span class="sxs-lookup"><span data-stu-id="136eb-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="136eb-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="136eb-106">To correct this error</span></span>  
  
- <span data-ttu-id="136eb-107">Verificare che la definizione del tipo e il relativo riferimento usino entrambi la stessa ortografia.</span><span class="sxs-lookup"><span data-stu-id="136eb-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
- <span data-ttu-id="136eb-108">Verificare che la definizione del tipo sia accessibile al riferimento.</span><span class="sxs-lookup"><span data-stu-id="136eb-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="136eb-109">Se, ad esempio, il tipo si trova in un altro modulo ed è stato dichiarato `Private` , spostare la definizione del tipo nel modulo di riferimento o dichiararlo `Public` .</span><span class="sxs-lookup"><span data-stu-id="136eb-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
- <span data-ttu-id="136eb-110">Verificare che lo spazio dei nomi del tipo non sia ridefinito all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="136eb-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="136eb-111">In caso contrario, utilizzare la `Global` parola chiave per qualificare completamente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="136eb-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="136eb-112">Se, ad esempio, un progetto definisce uno spazio dei nomi denominato `System` , <xref:System.Object?displayProperty=nameWithType> non è possibile accedere al tipo a meno che non sia completo con la `Global` parola chiave: `Global.System.Object` .</span><span class="sxs-lookup"><span data-stu-id="136eb-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
- <span data-ttu-id="136eb-113">Se il tipo è definito, ma la libreria di oggetti o la libreria dei tipi in cui è definita non è registrata in Visual Basic, fare clic su **Aggiungi riferimento** nel menu **progetto** , quindi selezionare la libreria di oggetti o la libreria dei tipi appropriata.</span><span class="sxs-lookup"><span data-stu-id="136eb-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
- <span data-ttu-id="136eb-114">Verificare che il tipo si trovi in un assembly che fa parte del profilo di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="136eb-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="136eb-115">Per altre informazioni, vedere [Risoluzione dei problemi relativi agli errori di impostazione di .NET Framework come destinazione](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="136eb-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="136eb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="136eb-116">See also</span></span>

- [<span data-ttu-id="136eb-117">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="136eb-117">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="136eb-118">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="136eb-118">Enum Statement</span></span>](../statements/enum-statement.md)
- [<span data-ttu-id="136eb-119">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="136eb-119">Structure Statement</span></span>](../statements/structure-statement.md)
- [<span data-ttu-id="136eb-120">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="136eb-120">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="136eb-121">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="136eb-121">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="136eb-122">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="136eb-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
