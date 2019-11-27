---
title: 'Procedura: chiamare API di Windows'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 6f3c53243d7aeb73be81796d5ca185c3a3c41c72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348706"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Procedura: chiamare API di Windows (Visual Basic)
Questo esempio definisce e chiama la funzione `MessageBox` in User32. dll e quindi passa una stringa a essa.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un riferimento allo spazio dei nomi <xref:System>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- Il metodo non è statico, è astratto oppure è stato definito in precedenza. Il tipo padre è un'interfaccia oppure la lunghezza del *nome* o *dllname* è zero. (<xref:System.ArgumentException>)  
  
- Il *nome* o *dllname* è `Nothing`. (<xref:System.ArgumentNullException>)  
  
- Il tipo contenitore è stato creato in precedenza con `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni dettagliate su platform invoke](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Esempi di platform invoke](../../../framework/interop/platform-invoke-examples.md)
- [Utilizzo di funzioni di DLL non gestite](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definizione di un metodo con Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)
