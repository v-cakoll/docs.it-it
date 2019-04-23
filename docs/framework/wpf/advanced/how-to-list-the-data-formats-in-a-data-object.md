---
title: 'Procedura: Elencare i formati dati in un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
ms.openlocfilehash: f8230eac33a18a0d99cc757d54c2b901c1afe977
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077745"
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a>Procedura: Elencare i formati dati in un oggetto dati
Gli esempi seguenti illustrano come usare il <xref:System.Windows.DataObject.GetFormats%2A> overload del metodo get di una matrice di stringhe che indicano di ogni formato di dati che è disponibile in un oggetto dati.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indicano tutti i formati di dati disponibili in un oggetto dati (nativo e conversione automatica).  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetFormats%2A> overload per ottenere una matrice di stringhe che indicano solo i formati di dati disponibili in un oggetto dati (auto-convertibili formati dati vengono filtrati).  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.IDataObject>
- [Cenni preliminari sul trascinamento della selezione](drag-and-drop-overview.md)
