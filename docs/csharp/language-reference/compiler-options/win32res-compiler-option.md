---
title: -win32res (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 3f7f5f323006024c393cb066284712ed60836372
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="e615e-102">-win32res (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="e615e-102">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="e615e-103">L'opzione **-win32res** inserisce una risorsa Win32 nel file di output.</span><span class="sxs-lookup"><span data-stu-id="e615e-103">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e615e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e615e-104">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="e615e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e615e-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="e615e-106">Il file di risorse da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="e615e-106">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e615e-107">Note</span><span class="sxs-lookup"><span data-stu-id="e615e-107">Remarks</span></span>  
 <span data-ttu-id="e615e-108">Un file di risorse Win32 può essere creato con il [compilatore di risorse](../../language-reference/compiler-options/resource-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e615e-108">A Win32 resource file can be created with the [Resource Compiler](../../language-reference/compiler-options/resource-compiler-option.md).</span></span> <span data-ttu-id="e615e-109">Il Compilatore di risorse viene richiamato quando si compila un programma Visual C++. Dal file .rc viene creato un file .res.</span><span class="sxs-lookup"><span data-stu-id="e615e-109">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="e615e-110">In una risorsa Win32 può essere contenute le informazioni sulla versione o sulla bitmap (icona) che consentono di identificare l'applicazione in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="e615e-110">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="e615e-111">Se non si specifica **-win32res**, il compilatore genererà le informazioni sulla versione in base alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e615e-111">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="e615e-112">Vedere [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (per fare riferimento a un file di risorse di .NET Framework) o a [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (per associarlo).</span><span class="sxs-lookup"><span data-stu-id="e615e-112">See [-linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [-resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e615e-113">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e615e-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e615e-114">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="e615e-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="e615e-115">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="e615e-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="e615e-116">Fare clic sul pulsante **File di risorse** e scegliere un file usando la casella combinata.</span><span class="sxs-lookup"><span data-stu-id="e615e-116">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e615e-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="e615e-117">Example</span></span>  
 <span data-ttu-id="e615e-118">Compilare `in.cs` e associare un file di risorse Win32 `rf.res` per produrre `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="e615e-118">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e615e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e615e-119">See Also</span></span>  
 [<span data-ttu-id="e615e-120">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="e615e-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="e615e-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="e615e-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
