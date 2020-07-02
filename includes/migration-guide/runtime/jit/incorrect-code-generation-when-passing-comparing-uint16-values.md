---
ms.openlocfilehash: c20d5fb3d700ba7649e423a79e4598b327c50a00
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622249"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Generazione di codice non corretto per il passaggio e il confronto di valori UInt16

#### <a name="details"></a>Dettagli

A causa di modifiche introdotte in .NET Framework 4.7, in alcuni casi il codice generato dal compilatore JIT nelle applicazioni in esecuzione in .NET Framework 4.7 confrontano in modo non corretto due valori <code>T:System.UInt16</code>. Per altre informazioni, vedere [Issue #11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508) (Problema n. 11508: Generazione automatica di codice non valido quando si passano e confrontano argomenti ushort) su GitHub.com.

#### <a name="suggestion"></a>Suggerimento

Se si verificano problemi nel confronto di valori senza segno a 16 bit in .NET Framework 4.7, eseguire l'aggiornamento a .NET Framework 4.7.1.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.7|
|Type|Runtime|
