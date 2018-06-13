---
title: Utilizzo dei contenitori di grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: 8755a95434d3fed06a55cfca0f71d86e5521cb39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525021"
---
# <a name="using-graphics-containers"></a><span data-ttu-id="854c4-102">Utilizzo dei contenitori di grafica</span><span class="sxs-lookup"><span data-stu-id="854c4-102">Using Graphics Containers</span></span>
<span data-ttu-id="854c4-103">Oggetto <xref:System.Drawing.Graphics> oggetto fornisce metodi, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, e <xref:System.Drawing.Graphics.DrawString%2A> per la visualizzazione di testo, immagini raster e immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="854c4-103">A <xref:System.Drawing.Graphics> object provides methods such as <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, and <xref:System.Drawing.Graphics.DrawString%2A> for displaying vector images, raster images, and text.</span></span> <span data-ttu-id="854c4-104">Oggetto <xref:System.Drawing.Graphics> oggetto dispone inoltre di diverse proprietà che determinano la qualità e l'orientamento degli elementi da cui vengono disegnate.</span><span class="sxs-lookup"><span data-stu-id="854c4-104">A <xref:System.Drawing.Graphics> object also has several properties that influence the quality and orientation of the items that are drawn.</span></span> <span data-ttu-id="854c4-105">Ad esempio, la proprietà modalità di arrotondamento determina se l'anti-aliasing viene applicato a linee e curve, e la proprietà di trasformazione world influenza la posizione e la rotazione di elementi che vengono disegnate.</span><span class="sxs-lookup"><span data-stu-id="854c4-105">For example, the smoothing mode property determines whether antialiasing is applied to lines and curves, and the world transformation property influences the position and rotation of the items that are drawn.</span></span>  
  
 <span data-ttu-id="854c4-106">Oggetto <xref:System.Drawing.Graphics> oggetto è associato a un particolare dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="854c4-106">A <xref:System.Drawing.Graphics> object is associated with a particular display device.</span></span> <span data-ttu-id="854c4-107">Quando si utilizza un <xref:System.Drawing.Graphics> oggetto da disegnare in una finestra di <xref:System.Drawing.Graphics> oggetto è anche associato a quel particolare finestra.</span><span class="sxs-lookup"><span data-stu-id="854c4-107">When you use a <xref:System.Drawing.Graphics> object to draw in a window, the <xref:System.Drawing.Graphics> object is also associated with that particular window.</span></span>  
  
 <span data-ttu-id="854c4-108">Oggetto <xref:System.Drawing.Graphics> oggetto può essere considerato come un contenitore poiché contiene un set di proprietà che influenza il disegno e collegarla a informazioni specifiche del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="854c4-108">A <xref:System.Drawing.Graphics> object can be thought of as a container because it holds a set of properties that influence drawing and it is linked to device-specific information.</span></span> <span data-ttu-id="854c4-109">È possibile creare un contenitore secondario all'interno di un oggetto esistente <xref:System.Drawing.Graphics> oggetto chiamando il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo che <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="854c4-109">You can create a secondary container within an existing <xref:System.Drawing.Graphics> object by calling the <xref:System.Drawing.Graphics.BeginContainer%2A> method of that <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="854c4-110">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="854c4-110">In This Section</span></span>  
 [<span data-ttu-id="854c4-111">Gestione dello stato di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="854c4-111">Managing the State of a Graphics Object</span></span>](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 <span data-ttu-id="854c4-112">Viene descritto come gestire le impostazioni relative alla qualità, area di ritaglio e trasformazioni di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="854c4-112">Describes how manage the quality settings, clipping area and transformations of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [<span data-ttu-id="854c4-113">Uso di contenitori di grafica annidati</span><span class="sxs-lookup"><span data-stu-id="854c4-113">Using Nested Graphics Containers</span></span>](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 <span data-ttu-id="854c4-114">Di seguito viene illustrato come utilizzare i contenitori per controllare lo stato del <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="854c4-114">Shows how to use containers to control the state of the <xref:System.Drawing.Graphics> object.</span></span>
