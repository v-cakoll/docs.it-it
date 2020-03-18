---
title: -subsystemversion (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: d76c9424340b4b6f3c211c849b466be55eb79d1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74802038"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="dbb92-102">-subsystemversion (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="dbb92-102">-subsystemversion (C# Compiler Options)</span></span>

<span data-ttu-id="dbb92-103">Specifica la versione minima del sottosistema in cui è possibile eseguire il file eseguibile generato, determinando le versioni di Windows in cui è possibile eseguire il file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="dbb92-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="dbb92-104">In genere, questa opzione assicura che il file eseguibile possa sfruttare le funzionalità di protezione che non sono disponibili con le versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="dbb92-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb92-105">Per specificare il sottosistema stesso, usare l'opzione del compilatore [-target](./target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="dbb92-105">To specify the subsystem itself, use the [-target](./target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="dbb92-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbb92-106">Syntax</span></span>

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="dbb92-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="dbb92-107">Parameters</span></span>

`major.minor`

<span data-ttu-id="dbb92-108">Versione minima richiesta per il sottosistema, espressa in una notazione del punto per le versioni principali e secondarie.</span><span class="sxs-lookup"><span data-stu-id="dbb92-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="dbb92-109">Ad esempio, è possibile specificare che un'applicazione non può essere eseguita su un sistema operativo precedente a Windows 7 Se si imposta il valore di questa opzione su 6.01, come descritto nella tabella più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dbb92-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="dbb92-110">È necessario specificare i valori per `major` e `minor` come numeri interi.</span><span class="sxs-lookup"><span data-stu-id="dbb92-110">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="dbb92-111">Gli zeri iniziali della versione `minor` non modificano la versione, a differenza degli zeri finali.</span><span class="sxs-lookup"><span data-stu-id="dbb92-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="dbb92-112">Ad esempio, 6.1 e 6.01 si fanno riferimento alla stessa versione, ma 6.10 fa riferimento a una versione diversa.</span><span class="sxs-lookup"><span data-stu-id="dbb92-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="dbb92-113">È consigliabile esprimere la versione secondaria con due cifre per evitare confusione.</span><span class="sxs-lookup"><span data-stu-id="dbb92-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbb92-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dbb92-114">Remarks</span></span>

<span data-ttu-id="dbb92-115">Nella tabella seguente sono elencate le versioni comuni del sottosistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="dbb92-115">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="dbb92-116">Versione di Windows</span><span class="sxs-lookup"><span data-stu-id="dbb92-116">Windows version</span></span>|<span data-ttu-id="dbb92-117">Versione del sottosistema</span><span class="sxs-lookup"><span data-stu-id="dbb92-117">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="dbb92-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="dbb92-118">Windows 2000</span></span>|<span data-ttu-id="dbb92-119">5,00</span><span class="sxs-lookup"><span data-stu-id="dbb92-119">5.00</span></span>|
|<span data-ttu-id="dbb92-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="dbb92-120">Windows XP</span></span>|<span data-ttu-id="dbb92-121">5,01</span><span class="sxs-lookup"><span data-stu-id="dbb92-121">5.01</span></span>|
|<span data-ttu-id="dbb92-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="dbb92-122">Windows Server 2003</span></span>|<span data-ttu-id="dbb92-123">5,02</span><span class="sxs-lookup"><span data-stu-id="dbb92-123">5.02</span></span>|
|<span data-ttu-id="dbb92-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="dbb92-124">Windows Vista</span></span>|<span data-ttu-id="dbb92-125">6,00</span><span class="sxs-lookup"><span data-stu-id="dbb92-125">6.00</span></span>|
|<span data-ttu-id="dbb92-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="dbb92-126">Windows 7</span></span>|<span data-ttu-id="dbb92-127">6.01</span><span class="sxs-lookup"><span data-stu-id="dbb92-127">6.01</span></span>|
|<span data-ttu-id="dbb92-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="dbb92-128">Windows Server 2008</span></span>|<span data-ttu-id="dbb92-129">6.01</span><span class="sxs-lookup"><span data-stu-id="dbb92-129">6.01</span></span>|
|<span data-ttu-id="dbb92-130">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dbb92-130">Windows 8</span></span>|<span data-ttu-id="dbb92-131">6.02</span><span class="sxs-lookup"><span data-stu-id="dbb92-131">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="dbb92-132">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="dbb92-132">Default values</span></span>

<span data-ttu-id="dbb92-133">Il valore predefinito dell'opzione del compilatore **-subsystemversion** dipende dalle condizioni elencate di seguito:</span><span class="sxs-lookup"><span data-stu-id="dbb92-133">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="dbb92-134">Il valore predefinito è 6.02 se è impostata un'opzione del compilatore nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="dbb92-134">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="dbb92-135">-target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="dbb92-135">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)

  - [<span data-ttu-id="dbb92-136">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="dbb92-136">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)

  - [<span data-ttu-id="dbb92-137">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="dbb92-137">-platform:arm</span></span>](./platform-compiler-option.md)

- <span data-ttu-id="dbb92-138">Il valore predefinito è 6.00 se si usa MSBuild, se la destinazione è .NET Framework 4.5 e se non è stata impostata una delle opzioni del compilatore specificate in precedenza in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="dbb92-138">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="dbb92-139">Il valore predefinito è 4.00 se nessuna di queste condizioni è vera.</span><span class="sxs-lookup"><span data-stu-id="dbb92-139">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="dbb92-140">Impostazione di questa opzione</span><span class="sxs-lookup"><span data-stu-id="dbb92-140">Setting this option</span></span>

<span data-ttu-id="dbb92-141">Per impostare l'opzione del compilatore **-subsystemversion** in Visual Studio, è necessario aprire il file con estensione csproj e specificare un valore per la proprietà `SubsystemVersion` nel codice XML di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="dbb92-141">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="dbb92-142">Non è possibile impostare questa opzione nell'IDE di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dbb92-142">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="dbb92-143">Per altre informazioni, vedere "Valori predefiniti" più indietro in questo argomento o [Proprietà di progetto MSBuild comuni](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="dbb92-143">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb92-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbb92-144">See also</span></span>

- [<span data-ttu-id="dbb92-145">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="dbb92-145">C# Compiler Options</span></span>](./index.md)
