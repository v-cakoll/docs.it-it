---
title: -win32res (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /win32res
dev_langs:
- CSharp
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
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
ms.openlocfilehash: 4552b526767584e62106b2b10f8a1e6394a23b46
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="win32res-c-compiler-options"></a><span data-ttu-id="78c7d-102">/win32res (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="78c7d-102">/win32res (C# Compiler Options)</span></span>
<span data-ttu-id="78c7d-103">L'opzione **/win32res** inserisce una risorsa Win32 nel file di output.</span><span class="sxs-lookup"><span data-stu-id="78c7d-103">The **/win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78c7d-104">Syntax</span></span>  
  
```console  
/win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="78c7d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="78c7d-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="78c7d-106">Il file di risorse da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="78c7d-106">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78c7d-107">Note</span><span class="sxs-lookup"><span data-stu-id="78c7d-107">Remarks</span></span>  
 <span data-ttu-id="78c7d-108">Un file di risorse Win32 può essere creato con il [compilatore di risorse](http://go.microsoft.com/fwlink/?LinkId=148370).</span><span class="sxs-lookup"><span data-stu-id="78c7d-108">A Win32 resource file can be created with the [Resource Compiler](http://go.microsoft.com/fwlink/?LinkId=148370).</span></span> <span data-ttu-id="78c7d-109">Il Compilatore di risorse viene richiamato quando si compila un programma Visual C++. Dal file .rc viene creato un file .res.</span><span class="sxs-lookup"><span data-stu-id="78c7d-109">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="78c7d-110">In una risorsa Win32 può essere contenute le informazioni sulla versione o sulla bitmap (icona) che consentono di identificare l'applicazione in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="78c7d-110">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="78c7d-111">Se non si specifica **/win32res**, il compilatore genererà le informazioni sulla versione in base alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="78c7d-111">If you do not specify **/win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="78c7d-112">Vedere [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (per fare riferimento a un file di risorse di .NET Framework) o [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (per associarlo).</span><span class="sxs-lookup"><span data-stu-id="78c7d-112">See [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) (to reference) or [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="78c7d-113">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="78c7d-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="78c7d-114">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="78c7d-114">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="78c7d-115">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="78c7d-115">Click the **Application** property page.</span></span>  
  
3.  <span data-ttu-id="78c7d-116">Fare clic sul pulsante **File di risorse** e scegliere un file usando la casella combinata.</span><span class="sxs-lookup"><span data-stu-id="78c7d-116">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78c7d-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="78c7d-117">Example</span></span>  
 <span data-ttu-id="78c7d-118">Compilare `in.cs` e associare un file di risorse Win32 `rf.res` per produrre `in.exe`:</span><span class="sxs-lookup"><span data-stu-id="78c7d-118">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc /win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="78c7d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78c7d-119">See Also</span></span>  
 <span data-ttu-id="78c7d-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="78c7d-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="78c7d-121">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="78c7d-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

