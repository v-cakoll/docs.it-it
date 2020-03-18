---
title: -doc (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: 01ea71f3de9e30abe25184e38a59f3707b54bd5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73422965"
---
# <a name="-doc-c-compiler-options"></a><span data-ttu-id="6bc0f-102">-doc (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="6bc0f-102">-doc (C# Compiler Options)</span></span>
<span data-ttu-id="6bc0f-103">L'opzione **-doc** consente di inserire commenti per la documentazione in un file XML.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-103">The **-doc** option allows you to place documentation comments in an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bc0f-104">Syntax</span></span>  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="6bc0f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6bc0f-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="6bc0f-106">File di output in XML, con i commenti presenti nei file del codice sorgente della compilazione.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-106">The output file for XML, which is populated with the comments in the source code files of the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bc0f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6bc0f-107">Remarks</span></span>  
 <span data-ttu-id="6bc0f-108">Nei file del codice sorgente è possibile elaborare e aggiungere al file XML i commenti di documentazione che precedono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6bc0f-108">In source code files, documentation comments that precede the following can be processed and added to the XML file:</span></span>  
  
- <span data-ttu-id="6bc0f-109">Tipi definiti dall'utente, ad esempio una [classe](../keywords/class.md), un [delegato](../builtin-types/reference-types.md#the-delegate-type) o un'[interfaccia](../keywords/interface.md)</span><span class="sxs-lookup"><span data-stu-id="6bc0f-109">Such user-defined types as a [class](../keywords/class.md), [delegate](../builtin-types/reference-types.md#the-delegate-type), or [interface](../keywords/interface.md)</span></span>  
  
- <span data-ttu-id="6bc0f-110">Membri quali un campo, un [evento](../keywords/event.md), una [proprietà](../../programming-guide/classes-and-structs/using-properties.md) o un metodo</span><span class="sxs-lookup"><span data-stu-id="6bc0f-110">Such members as a field, [event](../keywords/event.md), [property](../../programming-guide/classes-and-structs/using-properties.md), or method</span></span>  
  
 <span data-ttu-id="6bc0f-111">Il primo output inserito nel file XML è quello del file di codice sorgente che contiene Main.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-111">The source code file that contains Main is output first into the XML.</span></span>  
  
 <span data-ttu-id="6bc0f-112">Per usare il file XML generato con la funzionalità [IntelliSense](/visualstudio/ide/using-intellisense), assegnare al file XML lo stesso nome dell'assembly che si vuole supportare, quindi accertarsi che il file XML si trovi nella stessa directory dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-112">To use the generated .xml file for use with the [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the .xml file be the same as the assembly you want to support and then make sure the .xml file is in the same directory as the assembly.</span></span> <span data-ttu-id="6bc0f-113">In questo modo, quando si farà riferimento all'assembly nel progetto Visual Studio, verrà trovato anche il file XML.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-113">Thus, when the assembly is referenced in the Visual Studio project, the .xml file is found as well.</span></span> <span data-ttu-id="6bc0f-114">Per altre informazioni, vedere [Inserimento di commenti al codice XML](/visualstudio/ide/reference/generate-xml-documentation-comments).</span><span class="sxs-lookup"><span data-stu-id="6bc0f-114">See [Supplying Code Comments](/visualstudio/ide/reference/generate-xml-documentation-comments) and for more information.</span></span>  
  
 <span data-ttu-id="6bc0f-115">A meno che non si esechi \<la compilazione con [-target:module](./target-module-compiler-option.md), `file` conterrà \<i tag>assembly /assembly> che specificano il nome del file contenente il manifesto dell'assembly per il file di output della compilazione.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-115">Unless you compile with [-target:module](./target-module-compiler-option.md), `file` will contain \<assembly>\</assembly> tags specifying the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bc0f-116">L'opzione -doc può essere usata per tutti i file di input o, se definita in Impostazioni progetto, per tutti i file di un progetto.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-116">The -doc option applies to all input files; or, if set in the Project Settings, all files in the project.</span></span> <span data-ttu-id="6bc0f-117">Per disabilitare la visualizzazione degli avvisi relativi ai commenti di documentazione per una sezione di codice o un file specifico, usare [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span><span class="sxs-lookup"><span data-stu-id="6bc0f-117">To disable warnings related to documentation comments for a specific file or section of code, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).</span></span>  
  
 <span data-ttu-id="6bc0f-118">Per informazioni sulla generazione di documentazione da commenti presenti nel codice, vedere [Tag consigliati per i commenti relativi alla documentazione](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="6bc0f-118">See [Recommended Tags for Documentation Comments](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6bc0f-119">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6bc0f-119">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="6bc0f-120">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-120">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="6bc0f-121">Fare clic sulla scheda **Generazione**.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-121">Click the **Build** tab.</span></span>  
  
3. <span data-ttu-id="6bc0f-122">Modificare la proprietà **File di documentazione XML**.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-122">Modify the **XML documentation file** property.</span></span>  
  
 <span data-ttu-id="6bc0f-123">Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="6bc0f-123">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc0f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bc0f-124">See also</span></span>

- [<span data-ttu-id="6bc0f-125">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="6bc0f-125">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="6bc0f-126">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="6bc0f-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
