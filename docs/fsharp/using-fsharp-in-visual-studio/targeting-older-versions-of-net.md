---
title: Impostazione di .NET Framework 2.0 come destinazione in Windows 8
description: 'Informazioni sulla scelta di una versione precedente di .NET Framework quando si usa F #.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63989543-95c3-4ab7-81f3-3834a8b15010
ms.openlocfilehash: 2c0191267da5bee7b844c11cdee168ccfb3321c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="035e8-104">Definizione di versioni precedenti di .NET come destinazione</span><span class="sxs-lookup"><span data-stu-id="035e8-104">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="035e8-105">In questo articolo non è aggiornato con il più recente di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="035e8-105">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="035e8-106">Verrà eseguito un aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="035e8-106">It will be updated.</span></span>

<span data-ttu-id="035e8-107">Potrebbe essere visualizzato l'errore seguente se si tenta di destinazione di .NET Framework 2.0, 3.0 o 3.5 in F # del progetto quando Visual Studio è installato in Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="035e8-107">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="035e8-108">Questo errore è noto che si verifichi nella combinazione delle condizioni seguente:</span><span class="sxs-lookup"><span data-stu-id="035e8-108">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="035e8-109">Visual Studio è installato in Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="035e8-109">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="035e8-110">È stato abilitato .NET Framework 3.5 prima di installare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="035e8-110">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="035e8-111">Il progetto è destinato a .NET Framework 2.0, 3.0 o 3.5.</span><span class="sxs-lookup"><span data-stu-id="035e8-111">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="035e8-112">Quando si installa Visual Studio, rileva le versioni installate di .NET Framework e installa il Runtime 2.0 F # solo se .NET Framework 3.5 è installato e abilitato.</span><span class="sxs-lookup"><span data-stu-id="035e8-112">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="035e8-113">Risolvere l'errore</span><span class="sxs-lookup"><span data-stu-id="035e8-113">Resolving the Error</span></span>
<span data-ttu-id="035e8-114">Per correggere l'errore, è possibile destinazione una versione più recente di .NET Framework oppure è possibile abilitare .NET Framework 3.5 in Windows 8.1 e quindi installare il runtime di F # 2.0 eseguendo il programma di installazione per Visual Studio con il **ripristino** opzione.</span><span class="sxs-lookup"><span data-stu-id="035e8-114">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="035e8-115">Per abilitare .NET Framework 3.5 in Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="035e8-115">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="035e8-116">Nel **avviare** schermata, iniziare a immettere **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="035e8-116">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="035e8-117">Quando si immette il nome, il **Pannello di controllo** icona viene visualizzata sotto il **app** intestazione.</span><span class="sxs-lookup"><span data-stu-id="035e8-117">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="035e8-118">Scegliere il **Pannello di controllo** icona, scegliere il **programmi** icona e quindi scegliere il **o disattivazione delle funzionalità Windows attivare** collegamento.</span><span class="sxs-lookup"><span data-stu-id="035e8-118">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="035e8-119">Assicurarsi che il **.NET Framework 3.5 (include .NET 2.0 e 3.0)** casella di controllo è selezionata e quindi scegliere il **OK** pulsante.</span><span class="sxs-lookup"><span data-stu-id="035e8-119">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="035e8-120">Non è necessario selezionare le caselle di controllo per tutti i nodi figlio dei componenti facoltativi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="035e8-120">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="035e8-121">.NET Framework 3.5 è abilitata se non è stato già.</span><span class="sxs-lookup"><span data-stu-id="035e8-121">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="035e8-122">Per installare il runtime di F # 2.0</span><span class="sxs-lookup"><span data-stu-id="035e8-122">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="035e8-123">Nel Pannello di controllo, scegliere il **programmi** collegamento e quindi scegliere il **programmi e funzionalità** collegamento.</span><span class="sxs-lookup"><span data-stu-id="035e8-123">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="035e8-124">Nell'elenco dei programmi installati, selezionare l'edizione di Visual Studio è installato e quindi scegliere il **modifica** pulsante.</span><span class="sxs-lookup"><span data-stu-id="035e8-124">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="035e8-125">Dopo l'avvio dell'installazione, scegliere il **ripristino** pulsante.</span><span class="sxs-lookup"><span data-stu-id="035e8-125">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="035e8-126">Per ulteriori informazioni, vedere [installazione di Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span><span class="sxs-lookup"><span data-stu-id="035e8-126">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="035e8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="035e8-127">See Also</span></span>
[<span data-ttu-id="035e8-128">Visual F#</span><span class="sxs-lookup"><span data-stu-id="035e8-128">Visual F#</span></span>](../index.md)
