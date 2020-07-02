---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621331"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Gli oggetti Reflection non possono essere più passati dal codice gestito ai client DCOM out-of-process

#### <a name="details"></a>Dettagli

Gli oggetti di reflection non possono essere più passati dal codice gestito ai client DCOM out-of-process. Sono interessati i tipi seguenti:<ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><xref:System.Reflection.MemberInfo?displayProperty=fullName> e i tipi derivati, inclusi <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> e <xref:System.Reflection.TypeInfo?displayProperty=fullName></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</li></ul>Le chiamate a <code>IMarshal</code> per l'oggetto restituiscono <code>E_NOINTERFACE</code>.

#### <a name="suggestion"></a>Suggerimento

Aggiornare il codice di marshalling in modo che funzioni con oggetti non di reflection

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.6|
|Type|Runtime|
