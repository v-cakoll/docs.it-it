---
ms.openlocfilehash: c462c7b4ec8423ce8fd331d3cd31154283cf1f1d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620261"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>Gli overload Marshal.SizeOf and Marshal.PtrToStructure causano interruzioni del codice dinamico

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5.1, l'associazione dinamica per i metodi <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> o <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (ad esempio, tramite Windows PowerShell, IronPython o la parola chiave dynamic di C#) può causare eccezioni <code>MethodInvocationExceptions</code> perché sono stati aggiunti nuovi overload di questi metodi che potrebbero risultare ambigui per i motori di script.

#### <a name="suggestion"></a>Suggerimento

Aggiornare gli script per indicare chiaramente quale overload deve essere usato. Questa operazione può essere eseguita in genere tramite il cast esplicito dei parametri di tipo dei metodi su <xref:System.Type>. Vedere [questo collegamento](https://support.microsoft.com/kb/2909958/) per altri dettagli ed esempi per risolvere il problema.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5.1|
|Type|Runtime|
