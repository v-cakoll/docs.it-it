---
title: Utilizzo del doppio buffer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169912"
---
# <a name="using-double-buffering"></a><span data-ttu-id="2f886-102">Utilizzo del doppio buffer</span><span class="sxs-lookup"><span data-stu-id="2f886-102">Using Double Buffering</span></span>
<span data-ttu-id="2f886-103">È possibile utilizzare grafica a doppio buffer per ridurre lo sfarfallio in applicazioni che prevedono operazioni complesse di disegno.</span><span class="sxs-lookup"><span data-stu-id="2f886-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="2f886-104">.NET Framework include supporto predefinito per il doppio buffer oppure è possibile gestire ed eseguire il rendering della grafica manualmente.</span><span class="sxs-lookup"><span data-stu-id="2f886-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f886-105">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="2f886-105">In This Section</span></span>  
 [<span data-ttu-id="2f886-106">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="2f886-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="2f886-107">Introduce doppio buffering concetto e profili di supporto di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f886-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="2f886-108">Procedura: Ridurre lo sfarfallio nella grafica con il doppio Buffering per form e controlli</span><span class="sxs-lookup"><span data-stu-id="2f886-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="2f886-109">Viene illustrato come utilizzare l'impostazione predefinita il doppio buffer supporto in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f886-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="2f886-110">Procedura: Gestire manualmente le immagini memorizzate nel buffer</span><span class="sxs-lookup"><span data-stu-id="2f886-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="2f886-111">Viene illustrato come gestire il doppio buffer nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2f886-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="2f886-112">Procedura: Eseguire il rendering manuale di grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="2f886-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="2f886-113">Viene illustrato come eseguire il rendering di grafica a doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="2f886-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2f886-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="2f886-114">Reference</span></span>  
 <span data-ttu-id="2f886-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Metodo di controllo che abilita il buffering doppio.</span><span class="sxs-lookup"><span data-stu-id="2f886-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="2f886-116"><xref:System.Drawing.BufferedGraphicsContext> Fornisce metodi per la creazione di buffer di grafica.</span><span class="sxs-lookup"><span data-stu-id="2f886-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="2f886-117">Fornisce l'accesso al contesto di grafica memorizzata nel buffer per un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f886-117">Provides access to the buffered graphics context for a application domain.</span></span>
