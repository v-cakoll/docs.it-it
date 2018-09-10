---
title: -main (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 2f3c9daf98bfe77ea9462c8126f7a8368016875c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516666"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="0b44b-102">-main (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="0b44b-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="0b44b-103">Questa opzione specifica la classe che contiene il punto di ingresso al programma, quando più classi contengono un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="0b44b-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b44b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b44b-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b44b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0b44b-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="0b44b-106">Il tipo contenente il metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="0b44b-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="0b44b-107">Il nome della classe specificato deve essere completo. Deve includere lo spazio dei nomi completo che contiene la classe, seguito dal nome della classe.</span><span class="sxs-lookup"><span data-stu-id="0b44b-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="0b44b-108">Ad esempio, quando il metodo `Main` è all'interno della classe `Program` nello spazio dei nomi `MyApplication.Core`, l'opzione del compilatore deve essere `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="0b44b-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0b44b-109">Note</span><span class="sxs-lookup"><span data-stu-id="0b44b-109">Remarks</span></span>  
 <span data-ttu-id="0b44b-110">Se la compilazione include più tipi con un metodo [Main](../../../csharp/programming-guide/main-and-command-args/index.md), è possibile specificare il tipo che contiene il metodo **Main** che si vuole usare come punto di ingresso nel programma.</span><span class="sxs-lookup"><span data-stu-id="0b44b-110">If your compilation includes more than one type with a [Main](../../../csharp/programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="0b44b-111">Usare questa opzione solo durante la compilazione di un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="0b44b-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0b44b-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0b44b-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0b44b-113">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="0b44b-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="0b44b-114">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="0b44b-114">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="0b44b-115">Modificare la proprietà **Oggetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="0b44b-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="0b44b-116">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="0b44b-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b44b-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b44b-117">Example</span></span>  
 <span data-ttu-id="0b44b-118">Compilare `t2.cs` e `t3.cs` specificando che il metodo **Main** si trova in `Test2`:</span><span class="sxs-lookup"><span data-stu-id="0b44b-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b44b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b44b-119">See Also</span></span>

- [<span data-ttu-id="0b44b-120">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="0b44b-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="0b44b-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="0b44b-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
