---
title: Nome '<name>' non dichiarato
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3aadc49f91021409123550ba2712f1acf5b99d83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651025"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="d297f-102">Nome '\<nome >' non è dichiarato</span><span class="sxs-lookup"><span data-stu-id="d297f-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="d297f-103">Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.</span><span class="sxs-lookup"><span data-stu-id="d297f-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="d297f-104">**ID errore:** BC30451</span><span class="sxs-lookup"><span data-stu-id="d297f-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d297f-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d297f-105">To correct this error</span></span>  
  
1. <span data-ttu-id="d297f-106">Controllare l'ortografia del nome nell'istruzione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d297f-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="d297f-107">Visual Basic è tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia viene considerata come un nome completamente diverso.</span><span class="sxs-lookup"><span data-stu-id="d297f-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="d297f-108">Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.</span><span class="sxs-lookup"><span data-stu-id="d297f-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="d297f-109">Verificare di avere l'operatore di accesso ai membri (`.`) tra un oggetto e il relativo membro.</span><span class="sxs-lookup"><span data-stu-id="d297f-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="d297f-110">Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="d297f-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="d297f-111">Se invece si digita `TextBox1Text`, viene creato un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="d297f-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="d297f-112">Se l'ortografia sia corretta e la sintassi di accesso ai membri qualsiasi oggetto sia corretta, verificare che l'elemento è stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="d297f-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="d297f-113">Per altre informazioni, vedere [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="d297f-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="d297f-114">Se è stata dichiarata l'elemento di programmazione, controllare che si trova nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="d297f-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="d297f-115">Se l'istruzione di riferimento è di fuori dell'area di dichiarazione di elemento di programmazione, è necessario qualificare il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d297f-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="d297f-116">Per altre informazioni, vedere [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="d297f-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="d297f-117">Se non si usa un nome completo del tipo o un nome di tipi e membri (ad esempio, il codice fa riferimento a una proprietà come `MethodInfo.Name` invece di `System.Reflection.MethodInfo.Name`), aggiungere un' [istruzione Imports](../statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="d297f-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="d297f-118">Se si sta tentando di compilare un progetto in stile SDK (un progetto con un \*file con estensione vbproj che inizia con la riga `<Project Sdk="Microsoft.NET.Sdk">`) e il messaggio di errore fa riferimento a un tipo o membro nell'assembly VisualBasic, configurare l'applicazione per eseguire la compilazione con un riferimento alla libreria di Runtime di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d297f-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="d297f-119">Per impostazione predefinita, un subset della libreria è incorporato nell'assembly in un progetto basato su SDK.</span><span class="sxs-lookup"><span data-stu-id="d297f-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="d297f-120">Ad esempio, nell'esempio seguente non viene compilato perché il <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> metodo nebyla nalezena.</span><span class="sxs-lookup"><span data-stu-id="d297f-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="d297f-121">Non è incorporato nel subset di Runtime di Visual Basic incluso con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d297f-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   <span data-ttu-id="d297f-122">Per risolvere questo errore, aggiungere il `<VBRuntime>Default</VBRuntime>` elemento ai progetti `<PropertyGroup>` sezione, come i seguente di file di progetto Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d297f-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="d297f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d297f-123">See also</span></span>

- [<span data-ttu-id="d297f-124">Riepilogo delle dichiarazioni e delle costanti</span><span class="sxs-lookup"><span data-stu-id="d297f-124">Declarations and Constants Summary</span></span>](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="d297f-125">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d297f-125">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="d297f-126">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="d297f-126">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="d297f-127">Riferimenti a elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="d297f-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
