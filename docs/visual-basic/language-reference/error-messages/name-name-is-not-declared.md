---
title: Nome '<name>' non dichiarato
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 6fa4639b97e4314d8752ae520e94a58a189b7cbb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397168"
---
# <a name="name-name-is-not-declared"></a><span data-ttu-id="110bc-102">Nome '\<name>' non dichiarato</span><span class="sxs-lookup"><span data-stu-id="110bc-102">Name '\<name>' is not declared</span></span>
<span data-ttu-id="110bc-103">Un'istruzione fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.</span><span class="sxs-lookup"><span data-stu-id="110bc-103">A statement refers to a programming element, but the compiler cannot find an element with that exact name.</span></span>  
  
 <span data-ttu-id="110bc-104">**ID errore:** BC30451</span><span class="sxs-lookup"><span data-stu-id="110bc-104">**Error ID:** BC30451</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="110bc-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="110bc-105">To correct this error</span></span>  
  
1. <span data-ttu-id="110bc-106">Controllare l'ortografia del nome nell'istruzione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="110bc-106">Check the spelling of the name in the referring statement.</span></span> <span data-ttu-id="110bc-107">Visual Basic non fa distinzione tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia viene considerata un nome completamente diverso.</span><span class="sxs-lookup"><span data-stu-id="110bc-107">Visual Basic is case-insensitive, but any other variation in the spelling is regarded as a completely different name.</span></span> <span data-ttu-id="110bc-108">Si noti che il carattere di sottolineatura (`_`) fa parte del nome e quindi dell'ortografia.</span><span class="sxs-lookup"><span data-stu-id="110bc-108">Note that the underscore (`_`) is part of the name and therefore part of the spelling.</span></span>  
  
2. <span data-ttu-id="110bc-109">Verificare di disporre dell'operatore di accesso ai membri ( `.` ) tra un oggetto e il relativo membro.</span><span class="sxs-lookup"><span data-stu-id="110bc-109">Check that you have the member access operator (`.`) between an object and its member.</span></span> <span data-ttu-id="110bc-110">Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`.</span><span class="sxs-lookup"><span data-stu-id="110bc-110">For example, if you have a <xref:System.Windows.Forms.TextBox> control named `TextBox1`, to access its <xref:System.Windows.Forms.TextBoxBase.Text%2A> property you should type `TextBox1.Text`.</span></span> <span data-ttu-id="110bc-111">Se invece si digita `TextBox1Text`, viene creato un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="110bc-111">If instead you type `TextBox1Text`, you have created a different name.</span></span>  
  
3. <span data-ttu-id="110bc-112">Se l'ortografia è corretta e la sintassi di qualsiasi accesso ai membri dell'oggetto è corretta, verificare che l'elemento sia stato dichiarato.</span><span class="sxs-lookup"><span data-stu-id="110bc-112">If the spelling is correct and the syntax of any object member access is correct, verify that the element has been declared.</span></span> <span data-ttu-id="110bc-113">Per altre informazioni, vedere [elementi dichiarati](../../programming-guide/language-features/declared-elements/index.md).</span><span class="sxs-lookup"><span data-stu-id="110bc-113">For more information, see [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).</span></span>  
  
4. <span data-ttu-id="110bc-114">Se l'elemento di programmazione è stato dichiarato, verificare che sia nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="110bc-114">If the programming element has been declared, check that it is in scope.</span></span> <span data-ttu-id="110bc-115">Se l'istruzione di riferimento è esterna all'area che dichiara l'elemento di programmazione, potrebbe essere necessario qualificare il nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="110bc-115">If the referring statement is outside the region declaring the programming element, you might need to qualify the element name.</span></span> <span data-ttu-id="110bc-116">Per altre informazioni, vedere [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="110bc-116">For more information, see [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).</span></span>  

5. <span data-ttu-id="110bc-117">Se non si utilizza un tipo completo o un nome di membro (ad esempio, il codice fa riferimento a una proprietà come `MethodInfo.Name` anziché `System.Reflection.MethodInfo.Name` ), aggiungere un' [istruzione Imports](../statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="110bc-117">If you are not using a fully qualified type or type and member name (for example, your code refers to a property as `MethodInfo.Name` instead of `System.Reflection.MethodInfo.Name`), add an [Imports statement](../statements/imports-statement-net-namespace-and-type.md).</span></span>

6. <span data-ttu-id="110bc-118">Se si tenta di compilare un progetto in stile SDK (un progetto con un file con \* estensione vbproj che inizia con la riga `<Project Sdk="Microsoft.NET.Sdk">` ) e il messaggio di errore fa riferimento a un tipo o a un membro nell'assembly Microsoft. VisualBasic. dll, configurare l'applicazione in modo che venga compilata con un riferimento alla libreria di runtime Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="110bc-118">If you are attempting to compile an SDK-style project (a project with a \*.vbproj file that begins with the line `<Project Sdk="Microsoft.NET.Sdk">`), and the error message refers to a type or member in the Microsoft.VisualBasic.dll assembly, configure your application to compile with a reference to the Visual Basic Runtime Library.</span></span> <span data-ttu-id="110bc-119">Per impostazione predefinita, un subset della libreria è incorporato nell'assembly in un progetto di tipo SDK.</span><span class="sxs-lookup"><span data-stu-id="110bc-119">By default, a subset of the library is embedded in your assembly in an SDK-style project.</span></span>

   <span data-ttu-id="110bc-120">Ad esempio, l'esempio seguente non viene compilato perché <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> non è possibile trovare il metodo.</span><span class="sxs-lookup"><span data-stu-id="110bc-120">For example, the following example fails to compile because the <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> method cannot be found.</span></span> <span data-ttu-id="110bc-121">Non è incorporato nel subset del runtime Visual Basic incluso nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="110bc-121">It is not embedded in the subset of the Visual Basic Runtime included with your application.</span></span>  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   <span data-ttu-id="110bc-122">Per risolvere questo errore, aggiungere l' `<VBRuntime>Default</VBRuntime>` elemento alla sezione Projects `<PropertyGroup>` , come mostrato nel file di progetto Visual Basic seguente.</span><span class="sxs-lookup"><span data-stu-id="110bc-122">To address this error, add the `<VBRuntime>Default</VBRuntime>` element to the projects `<PropertyGroup>` section, as the following Visual Basic project file shows.</span></span>

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a><span data-ttu-id="110bc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="110bc-123">See also</span></span>

- [<span data-ttu-id="110bc-124">Riepilogo delle dichiarazioni e delle costanti</span><span class="sxs-lookup"><span data-stu-id="110bc-124">Declarations and Constants Summary</span></span>](../keywords/declarations-and-constants-summary.md)
- [<span data-ttu-id="110bc-125">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="110bc-125">Visual Basic Naming Conventions</span></span>](../../programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="110bc-126">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="110bc-126">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="110bc-127">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="110bc-127">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
