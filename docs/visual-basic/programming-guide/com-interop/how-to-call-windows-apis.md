---
title: 'Procedura: Chiamare le API di Windows (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 9eb667c8492c1e20b82e16ae8d640aee872969e5
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738643"
---
# <a name="how-to-call-windows-apis-visual-basic"></a>Procedura: Chiamare le API di Windows (Visual Basic)
In questo esempio definisce e chiama il `MessageBox` funzione in User32. dll e quindi passa una stringa a esso.  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un riferimento allo spazio dei nomi <xref:System>.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il metodo non è statico, è astratto o è stato definito in precedenza. Il tipo padre è un'interfaccia o la lunghezza di *name* oppure *dllName* è uguale a zero. (<xref:System.ArgumentException>)  
  
-   Il *name* oppure *dllName* è `Nothing`. (<xref:System.ArgumentNullException>)  
  
-   Il tipo contenitore è stato creato in precedenza con `CreateType`. (<xref:System.InvalidOperationException>)  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni dettagliate su platform invoke](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Esempi di platform invoke](../../../framework/interop/platform-invoke-examples.md)
- [Utilizzo di funzioni di DLL non gestite](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- [Definizione di un metodo tramite Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))
- [Procedura dettagliata: Chiamata delle API di Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md)
