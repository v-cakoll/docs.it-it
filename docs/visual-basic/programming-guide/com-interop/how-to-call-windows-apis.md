---
title: 'Procedura: Chiamare le API di Windows'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 2c3bb599b79575180eb2b0ec89453f01901f94c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396843"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Procedura: chiamare API di Windows (Visual Basic)
In questo esempio viene definita e chiamata la `MessageBox` funzione in User32. dll, quindi viene passata una stringa.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a>Compilare il codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il metodo non è statico, è astratto oppure è stato definito in precedenza. Il tipo padre è un'interfaccia oppure la lunghezza del *nome* o *dllname* è zero. (<xref:System.ArgumentException>)  
  
- Il *nome* o *dllname* è `Nothing` . (<xref:System.ArgumentNullException>)  
  
- Il tipo contenitore è stato creato in precedenza con `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni dettagliate su platform invoke](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Esempi di platform invoke](../../../framework/interop/platform-invoke-examples.md)
- [Utilizzo di funzioni di DLL non gestite](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definizione di un metodo tramite reflection emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Procedura dettagliata: Chiamata delle API di Windows](walkthrough-calling-windows-apis.md)
- [Interoperabilità COM](index.md)
