---
title: "Gestione di eccezioni per interoperabilità COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e894d07e77b929b1ea22df2d34e542544ec3b1f3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="handling-com-interop-exceptions"></a>Gestione di eccezioni per interoperabilità COM
Il codice gestito può essere integrato con il codice non gestito per la gestione delle eccezioni. Se un metodo genera un'eccezione nel codice gestito, Common Language Runtime può passare un valore HRESULT a un oggetto COM. Se un metodo non riesce nel codice non gestito, restituendo un HRESULT di errore, il runtime genera un'eccezione che può essere intercettata dal codice gestito.  
  
 Il runtime esegue automaticamente il mapping HRESULT dall'interoperabilità COM per le eccezioni più specifiche. Ad esempio, E_ACCESSDENIED diventa <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY diventa <xref:System.OutOfMemoryException>, e così via.  
  
 Se il valore HRESULT è un risultato personalizzato o se è noto al runtime, il runtime passa un oggetto generico <xref:System.Runtime.InteropServices.COMException> al client. La proprietà **ErrorCode** di **COMException** contiene il valore HRESULT.  
  
## <a name="working-with-ierrorinfo"></a>Uso di IErrorInfo  
 Quando un errore viene passato da COM al codice gestito, il runtime compila l'oggetto eccezione con informazioni sull'errore. Gli oggetti COM che supportano IErrorInfo e restituiscono valori HRESULT forniscono queste informazioni per le eccezioni del codice gestito. Ad esempio, il runtime esegue il mapping della descrizione dell'errore COM alla proprietà <xref:System.Exception.Message%2A> dell'eccezione. Se il valore HRESULT non fornisce alcuna informazione di errore, il runtime compila molte delle proprietà dell'eccezione con i valori predefiniti.  
  
 Se un metodo non riesce nel codice non gestito, un'eccezione può essere passata a un segmento di codice gestito. L'argomento [HRESULT ed eccezioni](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contiene una tabella che mostra il mapping di HRESULT a oggetti eccezione di runtime.  

## <a name="see-also"></a>Vedere anche
[Eccezioni](index.md) 
