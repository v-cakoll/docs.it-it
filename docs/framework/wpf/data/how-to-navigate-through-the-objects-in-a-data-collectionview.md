---
title: 'Procedura: Spostarsi tra gli oggetti nella visualizzazione di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 1507ab4db0c91b670d8bca754f6fd67d887c7041
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931501"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Procedura: Spostarsi tra gli oggetti nella visualizzazione di una raccolta dati
Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o di raggruppamento. Viste anche forniscono un concetto di puntatore al record corrente e consentono di spostare il puntatore del mouse. Questo esempio viene illustrato come ottenere l'oggetto corrente, nonché navigare tra gli oggetti in una raccolta di dati utilizzando la funzionalità fornita nel <xref:System.Windows.Data.CollectionView> classe.  
  
## <a name="example"></a>Esempio  
 In questo esempio `myCollectionView` è un <xref:System.Windows.Data.CollectionView> oggetto che rappresenta una visualizzazione in una raccolta associata.  
  
 Nell'esempio riportato di seguito `OnButton` è un gestore eventi per il `Previous` e `Next` pulsanti in un'applicazione, che sono disponibili pulsanti che consentono all'utente di esplorare la raccolta dei dati. Si noti che il <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> e <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> delle proprietà del report se il puntatore al record corrente si trova all'inizio e fine dell'elenco rispettivamente in modo che <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> e <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> può essere chiamato come appropriato.  
  
 Il <xref:System.Windows.Data.CollectionView.CurrentItem%2A> proprietà della vista viene eseguito il cast come un `Order` per restituire l'elemento corrente dell'ordine nella raccolta.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](data-binding-overview.md)
- [Ordinare i dati in una visualizzazione](how-to-sort-data-in-a-view.md)
- [Filtrare i dati di una visualizzazione](how-to-filter-data-in-a-view.md)
- [Ordinare e raggruppare dati con una visualizzazione in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
