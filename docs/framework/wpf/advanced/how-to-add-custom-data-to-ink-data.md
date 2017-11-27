---
title: 'Procedura: aggiungere dati personalizzati ai dati dell''input penna'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f266f3c98ca64c80ccbb669a1cc646321754579f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="ddbc8-102">Procedura: aggiungere dati personalizzati ai dati dell'input penna</span><span class="sxs-lookup"><span data-stu-id="ddbc8-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="ddbc8-103">È possibile aggiungere dati personalizzati per input penna che verrà salvato quando l'input penna viene salvato come formato di input penna serializzato (ISF).</span><span class="sxs-lookup"><span data-stu-id="ddbc8-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="ddbc8-104">È possibile salvare i dati personalizzati per il <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, o <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="ddbc8-105">La possibilità di salvare i dati personalizzati in tre oggetti offre la possibilità di decidere il modo migliore per salvare i dati.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="ddbc8-106">Tutte le tre classi utilizzano metodi simili per archiviare e accedere ai dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="ddbc8-107">Solo i tipi seguenti possono essere salvati come dati personalizzati:</span><span class="sxs-lookup"><span data-stu-id="ddbc8-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="ddbc8-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="ddbc8-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="ddbc8-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="ddbc8-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="ddbc8-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="ddbc8-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="ddbc8-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="ddbc8-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="ddbc8-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="ddbc8-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="ddbc8-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="ddbc8-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="ddbc8-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="ddbc8-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddbc8-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddbc8-121">Example</span></span>  
 <span data-ttu-id="ddbc8-122">Nell'esempio seguente viene illustrato come aggiungere e recuperare dati personalizzati da un <xref:System.Windows.Ink.StrokeCollection>.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="ddbc8-123">Nell'esempio seguente viene creata un'applicazione che consente di visualizzare un <xref:System.Windows.Controls.InkCanvas> e due pulsanti.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="ddbc8-124">Il pulsante, `switchAuthor`, consente due penne utilizzabile da due autori diversi.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="ddbc8-125">Pulsante `changePenColors` modificato il colore di ogni tratto sul <xref:System.Windows.Controls.InkCanvas> in base all'autore.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="ddbc8-126">L'applicazione definisce due <xref:System.Windows.Ink.DrawingAttributes> degli oggetti e aggiunge una proprietà personalizzata per ognuno dei quali indica autore che ha il <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="ddbc8-127">Quando l'utente fa clic `changePenColors`, l'applicazione modifica l'aspetto del tratto in base al valore della proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ddbc8-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
