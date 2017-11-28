---
title: 'Procedura: recuperare dati in un formato dati particolare'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e6513fd6d8d443b76059626c0e40991e35830c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a>Procedura: recuperare dati in un formato dati particolare
Nell'esempio seguente viene illustrato come recuperare i dati da un oggetto dati in un formato specificato.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> eseguire l'overload per controllare innanzitutto se formattare una data specificata è disponibile (in modo nativo o tramite conversione automatica); se il formato specificato non è disponibile, l'esempio recupera i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29> metodo.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Il codice di esempio seguente usa il <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload per verificare se un formato dati specificato è disponibile in modo nativo (formati di dati convertibili automaticamente sono filtrati); se il formato specificato non è disponibile, l'esempio recupera i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29>metodo.  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.IDataObject>  
 [Cenni preliminari sul trascinamento della selezione](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
