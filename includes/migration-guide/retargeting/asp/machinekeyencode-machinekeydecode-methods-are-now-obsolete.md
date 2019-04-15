---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234706"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>I metodi MachineKey.Encode e MachineKey.Decode sono ora obsoleti

|   |   |
|---|---|
|Dettagli|Questi metodi sono ora obsoleti. La compilazione del codice che chiama tali metodi genera un avviso del compilatore.|
|Suggerimento|Le alternative consigliate sono <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> e <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. In alternativa, è possibile eliminare gli avvisi di compilazione o evitarli usando un compilatore precedente. Le API sono ancora supportate.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
