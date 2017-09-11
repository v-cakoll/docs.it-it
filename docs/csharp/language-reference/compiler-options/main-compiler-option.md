---
title: -main (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /main
dev_langs:
- CSharp
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eee7ef4698f4b6bf7c90ff8e22a1a3ae106bec35
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="main-c-compiler-options"></a><span data-ttu-id="401fb-102">/main (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="401fb-102">/main (C# Compiler Options)</span></span>
<span data-ttu-id="401fb-103">Questa opzione specifica la classe che contiene il punto di ingresso al programma, quando più classi contengono un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="401fb-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="401fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="401fb-104">Syntax</span></span>  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="401fb-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="401fb-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="401fb-106">Il tipo contenente il metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="401fb-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="401fb-107">Note</span><span class="sxs-lookup"><span data-stu-id="401fb-107">Remarks</span></span>  
 <span data-ttu-id="401fb-108">Se la compilazione include più tipi con un metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md), è possibile specificare il tipo che contiene il metodo **Main** che si vuole usare come punto di ingresso nel programma.</span><span class="sxs-lookup"><span data-stu-id="401fb-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="401fb-109">Usare questa opzione solo durante la compilazione di un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="401fb-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="401fb-110">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="401fb-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="401fb-111">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="401fb-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="401fb-112">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="401fb-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="401fb-113">Modificare la proprietà **Oggetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="401fb-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="401fb-114">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="401fb-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="401fb-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="401fb-115">Example</span></span>  
 <span data-ttu-id="401fb-116">Compilare `t2.cs` e `t3.cs` specificando che il metodo **Main** si trova in `Test2`:</span><span class="sxs-lookup"><span data-stu-id="401fb-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="401fb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="401fb-117">See Also</span></span>  
 <span data-ttu-id="401fb-118">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="401fb-118">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="401fb-119">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="401fb-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

