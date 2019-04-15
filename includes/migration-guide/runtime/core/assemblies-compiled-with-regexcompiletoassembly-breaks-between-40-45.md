---
ms.openlocfilehash: 69b25db88c7580787bbb47fb0902b6bb072f8dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235735"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Interruzioni per gli assembly compilati con Regex.CompileToAssembly tra le versioni 4.0 e 4.5

|   |   |
|---|---|
|Dettagli|Se si crea con .NET Framework 4.5 un assembly di espressioni regolari compilate destinato a .NET Framework 4, quando si prova a usare una delle espressioni regolari dell'assembly in un sistema in cui è installato .NET Framework 4, viene generata un'eccezione.|
|Suggerimento|Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:<ul><li>Creare l'assembly che contiene le espressioni regolari con .NET Framework 4.</li><li>Usare un'espressione regolare interpretata.</li></ul>|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
