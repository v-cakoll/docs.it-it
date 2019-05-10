---
title: "Procedura: Aggiungere dati personalizzati ai dati dell'input penna"
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640861"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Procedura: Aggiungere dati personalizzati ai dati dell'input penna
È possibile aggiungere dati personalizzati all'input penna che verrà salvato quando l'input penna viene salvata come formato di input penna serializzato (Serialized Format).  È possibile salvare i dati personalizzati per il <xref:System.Windows.Ink.DrawingAttributes>, il <xref:System.Windows.Ink.StrokeCollection>, o <xref:System.Windows.Ink.Stroke>.  La possibilità di salvare i dati personalizzati nelle tre oggetti ti offre la possibilità di decidere il modo migliore per salvare i dati.  Tutte le tre classi usano metodi simili per archiviare e accedere ai dati personalizzati.  
  
 Solo i tipi seguenti possono essere salvati come dati personalizzati:  
  
- <xref:System.Boolean>  
  
- <xref:System.Boolean>[]  
  
- <xref:System.Byte>  
  
- <xref:System.Byte>[]  
  
- <xref:System.Char>  
  
- <xref:System.Char>[]  
  
- <xref:System.DateTime>  
  
- <xref:System.DateTime>[]  
  
- <xref:System.Decimal>  
  
- <xref:System.Decimal>[]  
  
- <xref:System.Double>  
  
- <xref:System.Double>[]  
  
- <xref:System.Int16>  
  
- <xref:System.Int16>[]  
  
- <xref:System.Int32>  
  
- <xref:System.Int32>[]  
  
- <xref:System.Int64>  
  
- <xref:System.Int64>[]  
  
- <xref:System.Single>  
  
- <xref:System.Single>[]  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <xref:System.UInt16>[]  
  
- <xref:System.UInt32>  
  
- <xref:System.UInt32>[]  
  
- <xref:System.UInt64>  
  
- <xref:System.UInt64>[]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere e recuperare i dati personalizzati da un <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 L'esempio seguente crea un'applicazione che visualizza un <xref:System.Windows.Controls.InkCanvas> e due pulsanti.  Il pulsante, `switchAuthor`, consente due penne utilizzabile dai due diversi autori.  Il pulsante `changePenColors` modifica il colore di ogni tratto nel <xref:System.Windows.Controls.InkCanvas> in base all'autore.  L'applicazione definisce due <xref:System.Windows.Ink.DrawingAttributes> degli oggetti e aggiunge una proprietà personalizzata per ognuno dei quali indica l'autore che ha tracciato la <xref:System.Windows.Ink.Stroke>.  Quando l'utente fa clic `changePenColors`, l'applicazione modifica l'aspetto del tratto a seconda del valore della proprietà personalizzata.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
