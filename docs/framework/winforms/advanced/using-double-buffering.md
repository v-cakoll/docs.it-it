---
title: Utilizzo del doppio buffer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d83846dcded620b74f7d276fd241a302cce1b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-double-buffering"></a><span data-ttu-id="6689b-102">Utilizzo del doppio buffer</span><span class="sxs-lookup"><span data-stu-id="6689b-102">Using Double Buffering</span></span>
<span data-ttu-id="6689b-103">È possibile utilizzare grafica a doppio buffer per ridurre lo sfarfallio nelle applicazioni che contengono operazioni di disegno complesse.</span><span class="sxs-lookup"><span data-stu-id="6689b-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="6689b-104">.NET Framework include supporto incorporato per il doppio buffer o è possibile gestire ed eseguire il rendering di grafica manualmente.</span><span class="sxs-lookup"><span data-stu-id="6689b-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6689b-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="6689b-105">In This Section</span></span>  
 [<span data-ttu-id="6689b-106">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="6689b-106">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="6689b-107">Introduce doppio buffering concetto e strutture di supporto di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6689b-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="6689b-108">Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli</span><span class="sxs-lookup"><span data-stu-id="6689b-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="6689b-109">Viene illustrato come utilizzare il valore predefinito il doppio buffer di supporto in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6689b-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="6689b-110">Procedura: Gestire manualmente le immagini memorizzate nel buffer</span><span class="sxs-lookup"><span data-stu-id="6689b-110">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="6689b-111">Viene illustrato come gestire il doppio buffer nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="6689b-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="6689b-112">Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="6689b-112">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="6689b-113">Viene illustrato come eseguire il rendering di grafica a doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="6689b-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6689b-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="6689b-114">Reference</span></span>  
 <span data-ttu-id="6689b-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="6689b-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="6689b-116">Metodo di controllo che attiva il doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="6689b-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="6689b-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="6689b-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="6689b-118">Fornisce metodi per la creazione di buffer di grafica.</span><span class="sxs-lookup"><span data-stu-id="6689b-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="6689b-119">Fornisce l'accesso al contesto di grafica memorizzata nel buffer per un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="6689b-119">Provides access to the buffered graphics context for a application domain.</span></span>
