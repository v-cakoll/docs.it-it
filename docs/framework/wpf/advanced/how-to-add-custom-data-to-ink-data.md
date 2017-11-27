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
# <a name="how-to-add-custom-data-to-ink-data"></a>Procedura: aggiungere dati personalizzati ai dati dell'input penna
È possibile aggiungere dati personalizzati per input penna che verrà salvato quando l'input penna viene salvato come formato di input penna serializzato (ISF).  È possibile salvare i dati personalizzati per il <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, o <xref:System.Windows.Ink.Stroke>.  La possibilità di salvare i dati personalizzati in tre oggetti offre la possibilità di decidere il modo migliore per salvare i dati.  Tutte le tre classi utilizzano metodi simili per archiviare e accedere ai dati personalizzati.  
  
 Solo i tipi seguenti possono essere salvati come dati personalizzati:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>[]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>[]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>[]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>[]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>[]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>[]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>[]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>[]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>[]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>[]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>[]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>[]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>[]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere e recuperare dati personalizzati da un <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 Nell'esempio seguente viene creata un'applicazione che consente di visualizzare un <xref:System.Windows.Controls.InkCanvas> e due pulsanti.  Il pulsante, `switchAuthor`, consente due penne utilizzabile da due autori diversi.  Pulsante `changePenColors` modificato il colore di ogni tratto sul <xref:System.Windows.Controls.InkCanvas> in base all'autore.  L'applicazione definisce due <xref:System.Windows.Ink.DrawingAttributes> degli oggetti e aggiunge una proprietà personalizzata per ognuno dei quali indica autore che ha il <xref:System.Windows.Ink.Stroke>.  Quando l'utente fa clic `changePenColors`, l'applicazione modifica l'aspetto del tratto in base al valore della proprietà personalizzata.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
