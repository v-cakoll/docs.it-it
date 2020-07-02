---
title: Esempi di platform invoke
description: Vedere un platform invoke esempio in cui viene illustrato come definire e chiamare la funzione MessageBox in User32.dll.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
ms.openlocfilehash: 97b0720b8954bc24a4058e6a03c32d32bd9e3180
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620807"
---
# <a name="platform-invoke-examples"></a>Esempi di platform invoke
Gli esempi seguenti dimostrano come definire e chiamare la funzione **MessageBox** in User32.dll, passando una stringa semplice come argomento. Negli esempi, il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> è impostato su **Auto** per consentire alla piattaforma di destinazione di determinare la larghezza del carattere e il marshalling delle stringhe.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 Per ulteriori esempi, vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Creazione di prototipi nel codice gestito](creating-prototypes-in-managed-code.md)
- [Specifica di un set di caratteri](specifying-a-character-set.md)
