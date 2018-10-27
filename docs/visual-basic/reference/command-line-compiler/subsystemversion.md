---
title: -subsystemversion (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: 9c4b4d66ba002e58af87ef39ea82a7a23caa15ca
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185758"
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="30793-102">-subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30793-102">-subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="30793-103">Specifica la versione minima del sottosistema in cui è possibile eseguire il file eseguibile generato, determinando le versioni di Windows in cui è possibile eseguire il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="30793-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="30793-104">In genere, questa opzione assicura che il file eseguibile possa sfruttare le funzionalità di protezione che non sono disponibili con le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="30793-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30793-105">Per specificare il sottosistema stesso, usare l'opzione del compilatore [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="30793-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30793-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30793-106">Syntax</span></span>  
  
```vb  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30793-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="30793-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="30793-108">Versione minima richiesta per il sottosistema, espressa in una notazione del punto per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="30793-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="30793-109">Ad esempio, è possibile specificare che un'applicazione non può essere eseguita su un sistema operativo precedente a Windows 7 Se si imposta il valore di questa opzione su 6.01, come descritto nella tabella più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="30793-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="30793-110">È necessario specificare i valori per `major` e `minor` come numeri interi.</span><span class="sxs-lookup"><span data-stu-id="30793-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="30793-111">Gli zeri iniziali della versione `minor` non modificano la versione, a differenza degli zeri finali.</span><span class="sxs-lookup"><span data-stu-id="30793-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="30793-112">Ad esempio, 6.1 e 6.01 si fanno riferimento alla stessa versione, ma 6.10 fa riferimento a una versione diversa.</span><span class="sxs-lookup"><span data-stu-id="30793-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="30793-113">È consigliabile esprimere la versione secondaria con due cifre per evitare confusione.</span><span class="sxs-lookup"><span data-stu-id="30793-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30793-114">Note</span><span class="sxs-lookup"><span data-stu-id="30793-114">Remarks</span></span>  
 <span data-ttu-id="30793-115">Nella tabella seguente sono elencate le versioni comuni del sottosistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="30793-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="30793-116">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="30793-116">Windows version</span></span>|<span data-ttu-id="30793-117">Versione del sottosistema</span><span class="sxs-lookup"><span data-stu-id="30793-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="30793-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="30793-118">Windows 2000</span></span>|<span data-ttu-id="30793-119">5.00</span><span class="sxs-lookup"><span data-stu-id="30793-119">5.00</span></span>|  
|<span data-ttu-id="30793-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="30793-120">Windows XP</span></span>|<span data-ttu-id="30793-121">5.01</span><span class="sxs-lookup"><span data-stu-id="30793-121">5.01</span></span>|  
|<span data-ttu-id="30793-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="30793-122">Windows Server 2003</span></span>|<span data-ttu-id="30793-123">5.02</span><span class="sxs-lookup"><span data-stu-id="30793-123">5.02</span></span>|  
|<span data-ttu-id="30793-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="30793-124">Windows Vista</span></span>|<span data-ttu-id="30793-125">6.00</span><span class="sxs-lookup"><span data-stu-id="30793-125">6.00</span></span>|  
|<span data-ttu-id="30793-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="30793-126">Windows 7</span></span>|<span data-ttu-id="30793-127">6.01</span><span class="sxs-lookup"><span data-stu-id="30793-127">6.01</span></span>|  
|<span data-ttu-id="30793-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="30793-128">Windows Server 2008</span></span>|<span data-ttu-id="30793-129">6.01</span><span class="sxs-lookup"><span data-stu-id="30793-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="30793-130">6.02</span><span class="sxs-lookup"><span data-stu-id="30793-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="30793-131">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="30793-131">Default values</span></span>  
 <span data-ttu-id="30793-132">Il valore predefinito dell'opzione del compilatore **-subsystemversion** dipende dalle condizioni elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="30793-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="30793-133">Il valore predefinito è 6.02 se è impostata un'opzione del compilatore nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="30793-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="30793-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="30793-134">-target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="30793-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="30793-135">-target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="30793-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="30793-136">-platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="30793-137">Il valore predefinito è 6.00 se si usa MSBuild, con destinazione [!INCLUDE[net_v45](~/includes/net-v45-md.md)], e non è stata impostata una delle opzioni del compilatore specificate in precedenza in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="30793-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="30793-138">Il valore predefinito è 4.00 se nessuna di queste condizioni è vera.</span><span class="sxs-lookup"><span data-stu-id="30793-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="30793-139">Impostazione di questa opzione</span><span class="sxs-lookup"><span data-stu-id="30793-139">Setting this option</span></span>  
 <span data-ttu-id="30793-140">Per impostare il **- subsystemversion** l'opzione del compilatore in Visual Studio, è necessario aprire il file con estensione vbproj e specificare un valore per il `SubsystemVersion` proprietà nel codice XML di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="30793-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="30793-141">Non è possibile impostare questa opzione nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="30793-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="30793-142">Per altre informazioni, vedere "Valori predefiniti" più indietro in questo argomento o [Proprietà di progetto MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="30793-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="30793-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30793-143">See Also</span></span>  
[<span data-ttu-id="30793-144">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30793-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="30793-145">Proprietà di MSBuild</span><span class="sxs-lookup"><span data-stu-id="30793-145">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
