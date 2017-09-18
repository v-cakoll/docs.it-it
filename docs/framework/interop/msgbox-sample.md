---
title: Esempio di MsgBox
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0f6ef3407c5f06e04d7a8b882a6458f236886dea
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="msgbox-sample"></a>Esempio di MsgBox
Questo esempio illustra come passare i tipi stringa per valore come parametri in e quando usare i campi <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> e <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.  
  
 L'esempio di MsgBox usa la seguente funzione non gestita, mostrata con la dichiarazione di funzione originale:  
  
-   Versione di **MessageBox** esportata da User32. dll.  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 In questo esempio, la classe `LibWrap` contiene un prototipo gestito per ogni funzione non gestita chiamata dalla classe `MsgBoxSample`. I metodi del prototipo gestiti `MsgBox`, `MsgBox2` e `MsgBox3` hanno dichiarazioni diverse per la stessa funzione non gestita.  
  
 La dichiarazione per `MsgBox2` produce output non corretto nella finestra di messaggio perché il tipo di carattere, specificato come ANSI, non corrisponde al punto di ingresso `MessageBoxW`, ovvero il nome della funzione Unicode. La dichiarazione per `MsgBox3` crea una mancata corrispondenza tra i campi **EntryPoint**, **CharSet** e **ExactSpelling**. La chiamata di `MsgBox3` genera un'eccezione. Per informazioni dettagliate sulla denominazione delle stringhe e sul marshalling dei nomi, vedere [Specifica di un set di caratteri](../../../docs/framework/interop/specifying-a-character-set.md).  
  
## <a name="declaring-prototypes"></a>Dichiarazione dei prototipi  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)] [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)] [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a>Chiamata delle funzioni  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)] [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)] [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a>Vedere anche  
 [Marshalling di stringhe](../../../docs/framework/interop/marshaling-strings.md)   
 [Tipi di dati platform invoke](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshalling predefinito per le stringhe](../../../docs/framework/interop/default-marshaling-for-strings.md)   
 [Creazione di prototipi nel codice gestito](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Specifica di un set di caratteri](../../../docs/framework/interop/specifying-a-character-set.md)

