---
title: Esempio di MsgBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c4100bb3bafdfe141dc746a64ebd8172ebe3bce
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648583"
---
# <a name="msgbox-sample"></a>Esempio di MsgBox
Questo esempio illustra come passare i tipi stringa per valore come parametri in e quando usare i campi <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> e <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 L'esempio di MsgBox usa la seguente funzione non gestita, mostrata con la dichiarazione di funzione originale:  
  
- Versione di **MessageBox** esportata da User32. dll.  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 In questo esempio, la classe `LibWrap` contiene un prototipo gestito per ogni funzione non gestita chiamata dalla classe `MsgBoxSample`. I metodi del prototipo gestiti `MsgBox`, `MsgBox2` e `MsgBox3` hanno dichiarazioni diverse per la stessa funzione non gestita.  
  
 La dichiarazione per `MsgBox2` produce output non corretto nella finestra di messaggio perché il tipo di carattere, specificato come ANSI, non corrisponde al punto di ingresso `MessageBoxW`, ovvero il nome della funzione Unicode. La dichiarazione per `MsgBox3` crea una mancata corrispondenza tra i campi **EntryPoint**, **CharSet** e **ExactSpelling**. La chiamata di `MsgBox3` genera un'eccezione. Per informazioni dettagliate sulla denominazione delle stringhe e sul marshalling dei nomi, vedere [Specifica di un set di caratteri](specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Dichiarazione dei prototipi  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Chiamata delle funzioni  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Marshalling di stringhe](marshaling-strings.md)
- [Marshalling predefinito per le stringhe](default-marshaling-for-strings.md)
- [Creazione di prototipi nel codice gestito](creating-prototypes-in-managed-code.md)
- [Specifica di un set di caratteri](specifying-a-character-set.md)
