---
title: -checked (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: 44dc0fc8f50e5248ce2fca17c36f7309a6aca8d1
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239692"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="66447-102">-checked (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="66447-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="66447-103">L'opzione **-checked** specifica se un'istruzione di calcolo di interi che risulta in un valore non incluso nell'intervallo dei tipi di dati e nell'ambito di una parola chiave [checked](../keywords/checked.md) o [unchecked](../keywords/unchecked.md) genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66447-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../keywords/checked.md) or [unchecked](../keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66447-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66447-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="66447-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="66447-105">Remarks</span></span>  
 <span data-ttu-id="66447-106">Un'istruzione di calcolo di interi inclusa nell'ambito di una parola chiave `checked` o `unchecked` non è soggetta all'opzione **-checked**.</span><span class="sxs-lookup"><span data-stu-id="66447-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="66447-107">Se un'istruzione di calcolo di interi che non è compresa nell'ambito di una parola chiave `checked` o `unchecked` risulta in un valore non incluso nell'intervallo del tipo di dati e l'opzione **-checked+** (o **-checked**) viene usata nella compilazione, tale istruzione genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66447-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="66447-108">Se l'opzione **-checked-** viene usata nella compilazione, tale istruzione non genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66447-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="66447-109">Il valore predefinito per questa opzione è **-checked-**; il controllo dell'overflow è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="66447-109">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>
 
 <span data-ttu-id="66447-110">In alcuni casi gli strumenti automatici usati per compilare applicazioni di grandi dimensioni impostano l'opzione -checked su +.</span><span class="sxs-lookup"><span data-stu-id="66447-110">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="66447-111">Uno scenario per usare l'opzione -checked- consiste nell'eseguire l'override del valore predefinito globale dello strumento specificando -checked-.</span><span class="sxs-lookup"><span data-stu-id="66447-111">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>
 
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="66447-112">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66447-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="66447-113">Aprire la pagine **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="66447-113">Open the project's **Properties** page.</span></span> <span data-ttu-id="66447-114">Per altre informazioni, vedere [Pagina Compilazione, Creazione progetti (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="66447-114">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="66447-115">Fare clic sulla pagina delle proprietà **Compilazione**.</span><span class="sxs-lookup"><span data-stu-id="66447-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="66447-116">Fare clic sul pulsante **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="66447-116">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="66447-117">Modificare la proprietà **Controlla overflow aritmetico** .</span><span class="sxs-lookup"><span data-stu-id="66447-117">Modify the **Check for arithmetic overflow** property.</span></span>  
  
 <span data-ttu-id="66447-118">Per accedere all'opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="66447-118">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66447-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="66447-119">Example</span></span>  
 <span data-ttu-id="66447-120">Il comando seguente compila `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="66447-120">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="66447-121">L'uso di `-checked` nel comando specifica che l'istruzione di calcolo di interi nel file che non è nell'ambito della parola chiave `checked` o `unchecked` e che risulta in un valore non incluso nell'intervallo dei tipi di dati, genera un'eccezione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="66447-121">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="66447-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66447-122">See also</span></span>

- [<span data-ttu-id="66447-123">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="66447-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="66447-124">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="66447-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
