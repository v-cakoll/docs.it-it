---
title: 'Procedura: dichiarare eventi personalizzati per proteggere la memoria'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: c9a049d3f15d5620152f064888a97bd0be5d46b0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405131"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Procedura: dichiarare eventi personalizzati per proteggere la memoria (Visual Basic)
In alcuni casi è importante che un'applicazione mantenga l'utilizzo di memoria basso. Gli eventi personalizzati consentono all'applicazione di usare la memoria solo per gli eventi gestiti.  
  
 Per impostazione predefinita, quando una classe dichiara un evento, il compilatore alloca memoria per un campo per archiviare le informazioni sull'evento. Se una classe dispone di molti eventi non utilizzati, inutilmente si occupino di memoria.  
  
 Invece di usare l'implementazione predefinita di eventi forniti da Visual Basic, è possibile usare gli eventi personalizzati per gestire l'utilizzo della memoria con maggiore attenzione.  
  
## <a name="example"></a>Esempio  
 In questo esempio, la classe usa un'istanza della <xref:System.ComponentModel.EventHandlerList> classe, archiviata nel `Events` campo, per archiviare le informazioni sugli eventi in uso. La <xref:System.ComponentModel.EventHandlerList> classe è una classe di elenco ottimizzata progettata per ospitare delegati.  
  
 Tutti gli eventi nella classe usano il `Events` campo per tenere traccia dei metodi che gestiscono ogni evento.  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.EventHandlerList>
- [Events](index.md)
- [Procedura: dichiarare eventi personalizzati per evitare il blocco](how-to-declare-custom-events-to-avoid-blocking.md)
