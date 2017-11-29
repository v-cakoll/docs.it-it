---
title: -checked (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e02f82bb0dd2952bd2f192af7ff233194a045619
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="checked-c-compiler-options"></a><span data-ttu-id="9558e-102">/checked (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="9558e-102">/checked (C# Compiler Options)</span></span>
<span data-ttu-id="9558e-103">L'opzione **/checked** specifica se un'istruzione di calcolo di interi che risulta in un valore non incluso nell'intervallo dei tipi di dati e nell'ambito di una parola chiave [checked](../../../csharp/language-reference/keywords/checked.md) o [unchecked](../../../csharp/language-reference/keywords/unchecked.md) genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9558e-103">The **/checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9558e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9558e-104">Syntax</span></span>  
  
```console  
/checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="9558e-105">Note</span><span class="sxs-lookup"><span data-stu-id="9558e-105">Remarks</span></span>  
 <span data-ttu-id="9558e-106">Un'istruzione di calcolo di interi inclusa nell'ambito di una parola chiave `checked` o `unchecked` non è soggetta all'effetto della opzione **/checked**.</span><span class="sxs-lookup"><span data-stu-id="9558e-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **/checked** option.</span></span>  
  
 <span data-ttu-id="9558e-107">Se un'istruzione di calcolo di interi che non è nell'ambito di una parola chiave `checked` o `unchecked` risulta in un valore non incluso nell'intervallo del tipo di dati e l'opzione **/checked+** (**/checked**) viene usata nella compilazione, tale istruzione genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9558e-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **/checked+** (**/checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="9558e-108">Se l'opzione **/checked-** viene usata nella compilazione, tale istruzione non genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9558e-108">If **/checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="9558e-109">Il valore predefinito per questa opzione è **/checked-**.</span><span class="sxs-lookup"><span data-stu-id="9558e-109">The default value for this option is **/checked-**.</span></span> <span data-ttu-id="9558e-110">Uno scenario per l'uso di **/checked -** è la compilazione di applicazioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="9558e-110">One scenario for using **/checked-** is in building large applications.</span></span> <span data-ttu-id="9558e-111">Talvolta vengono usati strumenti automatizzati per compilare tali applicazioni e questi strumenti potrebbero impostare automaticamente **/checked** su +.</span><span class="sxs-lookup"><span data-stu-id="9558e-111">Sometimes automated tools are used to build such applications, and such a tool might automatically set **/checked** to +.</span></span> <span data-ttu-id="9558e-112">È possibile eseguire l'override del valore predefinito globale dello strumento specificando **/checked-**.</span><span class="sxs-lookup"><span data-stu-id="9558e-112">You can override the tool's global default by specifying **/checked-**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9558e-113">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9558e-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="9558e-114">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="9558e-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="9558e-115">Per altre informazioni, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="9558e-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="9558e-116">Fare clic sulla pagina della proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="9558e-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="9558e-117">Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="9558e-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="9558e-118">Modificare la proprietà **Controlla overflow/underflow aritmetico**.</span><span class="sxs-lookup"><span data-stu-id="9558e-118">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="9558e-119">Per accedere all'opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="9558e-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9558e-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="9558e-120">Example</span></span>  
 <span data-ttu-id="9558e-121">Il comando seguente compila `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="9558e-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="9558e-122">L'uso di `/checked` nel comando specifica che l'istruzione di calcolo di interi nel file che non è nell'ambito della parola chiave `checked` o `unchecked` e che risulta in un valore non incluso nell'intervallo dei tipi di dati, genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9558e-122">The use of `/checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="9558e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9558e-123">See Also</span></span>  
 [<span data-ttu-id="9558e-124">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="9558e-124">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="9558e-125">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="9558e-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
