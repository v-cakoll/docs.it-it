---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622044"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Alcune API .NET causano eccezioni EntryPointNotFoundException first-chance gestite

#### <a name="details"></a>Dettagli

In .NET Framework 4.5, un numero limitato di metodi .NET ha iniziato a generare eccezioni <xref:System.EntryPointNotFoundException?displayProperty=fullName> first-chance. Queste eccezioni erano gestite all'interno di .NET Framework, ma potevano interrompere l'automazione dei test che non prevedevano eccezioni first-chance. Queste stesse API causano errori in alcuni scenari di ApiVerifier con HighVersionLie abilitato.

#### <a name="suggestion"></a>Suggerimento

È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1. In alternativa, è possibile aggiornare l'automazione dei test in modo che non si interrompa in corrispondenza della prima <xref:System.EntryPointNotFoundException?displayProperty=fullName> first-chance.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
