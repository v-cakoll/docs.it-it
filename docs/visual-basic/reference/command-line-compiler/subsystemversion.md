---
title: /subsystemversion (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: efeade3fcde18f02b3a760adc50d3555df6c9ed7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="subsystemversion-visual-basic"></a><span data-ttu-id="45d5c-102">/subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45d5c-102">/subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="45d5c-103">Specifica la versione minima del sottosistema in cui è possibile eseguire il file eseguibile generato, in modo da determinare le versioni di Windows in cui è possibile eseguire il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="45d5c-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="45d5c-104">In genere, questa opzione assicura che il file eseguibile può sfruttare le funzionalità di protezione che non sono disponibili con le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="45d5c-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45d5c-105">Per specificare il sottosistema di se stesso, utilizzare il [/destinazione](../../../csharp/language-reference/compiler-options/target-compiler-option.md) l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="45d5c-105">To specify the subsystem itself, use the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d5c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45d5c-106">Syntax</span></span>  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45d5c-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="45d5c-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="45d5c-108">La versione minima del sottosistema, espresso in una notazione del punto per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="45d5c-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="45d5c-109">Ad esempio, è possibile specificare che un'applicazione non può eseguire su un sistema operativo precedente a Windows 7 Se si imposta il valore di questa opzione su 6.01, come descritto nella tabella più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="45d5c-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="45d5c-110">È necessario specificare i valori per `major` e `minor` come numeri interi.</span><span class="sxs-lookup"><span data-stu-id="45d5c-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="45d5c-111">Gli zero iniziali di `minor` versione non modifica la versione, ma si gli zeri finali.</span><span class="sxs-lookup"><span data-stu-id="45d5c-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="45d5c-112">Ad esempio, 6.1 e 6.01 si riferiscono alla stessa versione, ma 6.10 fa riferimento a una versione diversa.</span><span class="sxs-lookup"><span data-stu-id="45d5c-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="45d5c-113">È consigliabile esprimere la versione secondaria con due cifre per evitare confusione.</span><span class="sxs-lookup"><span data-stu-id="45d5c-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45d5c-114">Note</span><span class="sxs-lookup"><span data-stu-id="45d5c-114">Remarks</span></span>  
 <span data-ttu-id="45d5c-115">Nella tabella seguente sono elencate le versioni di sottosistema comune di Windows.</span><span class="sxs-lookup"><span data-stu-id="45d5c-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="45d5c-116">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="45d5c-116">Windows version</span></span>|<span data-ttu-id="45d5c-117">Versione del sottosistema</span><span class="sxs-lookup"><span data-stu-id="45d5c-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="45d5c-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="45d5c-118">Windows 2000</span></span>|<span data-ttu-id="45d5c-119">5.00</span><span class="sxs-lookup"><span data-stu-id="45d5c-119">5.00</span></span>|  
|<span data-ttu-id="45d5c-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="45d5c-120">Windows XP</span></span>|<span data-ttu-id="45d5c-121">5.01</span><span class="sxs-lookup"><span data-stu-id="45d5c-121">5.01</span></span>|  
|<span data-ttu-id="45d5c-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="45d5c-122">Windows Server 2003</span></span>|<span data-ttu-id="45d5c-123">5.02</span><span class="sxs-lookup"><span data-stu-id="45d5c-123">5.02</span></span>|  
|<span data-ttu-id="45d5c-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="45d5c-124">Windows Vista</span></span>|<span data-ttu-id="45d5c-125">6.00</span><span class="sxs-lookup"><span data-stu-id="45d5c-125">6.00</span></span>|  
|<span data-ttu-id="45d5c-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="45d5c-126">Windows 7</span></span>|<span data-ttu-id="45d5c-127">6.01</span><span class="sxs-lookup"><span data-stu-id="45d5c-127">6.01</span></span>|  
|<span data-ttu-id="45d5c-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="45d5c-128">Windows Server 2008</span></span>|<span data-ttu-id="45d5c-129">6.01</span><span class="sxs-lookup"><span data-stu-id="45d5c-129">6.01</span></span>|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|<span data-ttu-id="45d5c-130">6.02</span><span class="sxs-lookup"><span data-stu-id="45d5c-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="45d5c-131">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="45d5c-131">Default values</span></span>  
 <span data-ttu-id="45d5c-132">Il valore predefinito di **/subsystemversion** l'opzione del compilatore dipende dalle condizioni elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="45d5c-132">The default value of the **/subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="45d5c-133">Il valore predefinito è 6.02 se è impostata un'opzione del compilatore nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="45d5c-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="45d5c-134">/target: appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="45d5c-134">/target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="45d5c-135">/target: winmdobj</span><span class="sxs-lookup"><span data-stu-id="45d5c-135">/target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="45d5c-136">/platform:ARM</span><span class="sxs-lookup"><span data-stu-id="45d5c-136">/platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="45d5c-137">Il valore predefinito è 6.00 se si utilizza MSBuild, destinazione [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], e non è stata impostata una delle opzioni del compilatore che sono state specificate in precedenza in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="45d5c-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="45d5c-138">Il valore predefinito è 4.00 se nessuna di queste condizioni è vera.</span><span class="sxs-lookup"><span data-stu-id="45d5c-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="45d5c-139">Impostazione di questa opzione</span><span class="sxs-lookup"><span data-stu-id="45d5c-139">Setting this option</span></span>  
 <span data-ttu-id="45d5c-140">Per impostare il **/subsystemversion** l'opzione del compilatore in Visual Studio, è necessario aprire il file VBPROJ e specificare un valore per la `SubsystemVersion` proprietà nel codice XML di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="45d5c-140">To set the **/subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="45d5c-141">È possibile impostare questa opzione nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="45d5c-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="45d5c-142">Per ulteriori informazioni, vedere "Valori predefiniti" più indietro in questo argomento o [proprietà di progetto MSBuild comuni](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="45d5c-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="45d5c-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45d5c-143">See Also</span></span>  
[<span data-ttu-id="45d5c-144">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45d5c-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="45d5c-145">Proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="45d5c-145">MSBuild Properties</span></span>](https://docs.microsoft.com/visualstudio/msbuild/msbuild-properties)

