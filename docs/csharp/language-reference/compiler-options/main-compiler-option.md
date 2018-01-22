---
title: -main (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5f1d06bf408f13a78df503ab10fe3c57b4ff68a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="3abd6-102">-main (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="3abd6-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="3abd6-103">Questa opzione specifica la classe che contiene il punto di ingresso al programma, quando più classi contengono un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="3abd6-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abd6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3abd6-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="3abd6-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3abd6-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="3abd6-106">Il tipo contenente il metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="3abd6-106">The type that contains the **Main** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3abd6-107">Note</span><span class="sxs-lookup"><span data-stu-id="3abd6-107">Remarks</span></span>  
 <span data-ttu-id="3abd6-108">Se la compilazione include più tipi con un metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md), è possibile specificare il tipo che contiene il metodo **Main** che si vuole usare come punto di ingresso nel programma.</span><span class="sxs-lookup"><span data-stu-id="3abd6-108">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="3abd6-109">Usare questa opzione solo durante la compilazione di un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="3abd6-109">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3abd6-110">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3abd6-110">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="3abd6-111">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="3abd6-111">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="3abd6-112">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="3abd6-112">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="3abd6-113">Modificare la proprietà **Oggetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="3abd6-113">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="3abd6-114">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="3abd6-114">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3abd6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="3abd6-115">Example</span></span>  
 <span data-ttu-id="3abd6-116">Compilare `t2.cs` e `t3.cs` specificando che il metodo **Main** si trova in `Test2`:</span><span class="sxs-lookup"><span data-stu-id="3abd6-116">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="3abd6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3abd6-117">See Also</span></span>  
 [<span data-ttu-id="3abd6-118">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="3abd6-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="3abd6-119">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="3abd6-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
