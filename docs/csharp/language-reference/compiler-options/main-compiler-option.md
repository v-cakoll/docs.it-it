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
ms.openlocfilehash: 1de3d51953b632e3881db76202b63d3f287b39fe
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051870"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="367f6-102">-main (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="367f6-102">-main (C# Compiler Options)</span></span>

<span data-ttu-id="367f6-103">Questa opzione specifica la classe che contiene il punto di ingresso al programma, quando più classi contengono un metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="367f6-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="367f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="367f6-104">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="367f6-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="367f6-105">Arguments</span></span>
 `class`  
 <span data-ttu-id="367f6-106">Il tipo contenente il metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="367f6-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="367f6-107">Il nome della classe specificato deve essere completo. Deve includere lo spazio dei nomi completo che contiene la classe, seguito dal nome della classe.</span><span class="sxs-lookup"><span data-stu-id="367f6-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="367f6-108">Ad esempio, quando il metodo `Main` è all'interno della classe `Program` nello spazio dei nomi `MyApplication.Core`, l'opzione del compilatore deve essere `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="367f6-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="367f6-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="367f6-109">Remarks</span></span>

<span data-ttu-id="367f6-110">Se la compilazione include più tipi con un metodo [Main](../../programming-guide/main-and-command-args/index.md), è possibile specificare il tipo che contiene il metodo **Main** che si vuole usare come punto di ingresso nel programma.</span><span class="sxs-lookup"><span data-stu-id="367f6-110">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="367f6-111">Questa opzione è utilizzabile quando si compila un file con estensione *exe* .</span><span class="sxs-lookup"><span data-stu-id="367f6-111">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="367f6-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="367f6-112">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="367f6-113">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="367f6-113">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="367f6-114">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="367f6-114">Click the **Application** property page.</span></span>

3. <span data-ttu-id="367f6-115">Modificare la proprietà **Oggetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="367f6-115">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="367f6-116">Per impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="367f6-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="367f6-117">Per impostare questa opzione del compilatore modificando manualmente il file con *estensione csproj*</span><span class="sxs-lookup"><span data-stu-id="367f6-117">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="367f6-118">Per impostare questa opzione, è possibile modificare il file con estensione csproj e aggiungere un elemento `StartupObject` nella `PropertyGroup` sezione.</span><span class="sxs-lookup"><span data-stu-id="367f6-118">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="367f6-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="367f6-119">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="367f6-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="367f6-120">Example</span></span>

<span data-ttu-id="367f6-121">Compilare `t2.cs` e `t3.cs` specificando che il metodo **Main** si trova in `Test2`:</span><span class="sxs-lookup"><span data-stu-id="367f6-121">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="367f6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="367f6-122">See also</span></span>

- [<span data-ttu-id="367f6-123">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="367f6-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="367f6-124">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="367f6-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
