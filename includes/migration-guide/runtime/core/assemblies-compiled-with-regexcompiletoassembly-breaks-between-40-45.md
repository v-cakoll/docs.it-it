---
ms.openlocfilehash: 0bd90b3d479a7e0897aaf78b7718ae156a4a239f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620191"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Interruzioni per gli assembly compilati con Regex.CompileToAssembly tra le versioni 4.0 e 4.5

#### <a name="details"></a>Dettagli

Se si crea con .NET Framework 4.5 un assembly di espressioni regolari compilate destinato a .NET Framework 4, quando si prova a usare una delle espressioni regolari dell'assembly in un sistema in cui è installato .NET Framework 4, viene generata un'eccezione.

#### <a name="suggestion"></a>Suggerimento

Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:<ul><li>Creare l'assembly che contiene le espressioni regolari con .NET Framework 4.</li><li>Usare un'espressione regolare interpretata.</li></ul>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
