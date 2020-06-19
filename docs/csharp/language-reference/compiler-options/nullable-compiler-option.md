---
title: -Nullable (opzioni del compilatore C#)
ms.date: 06/04/2020
f1_keywords:
- /nullable
helpviewer_keywords:
- nullable compiler option [C#]
- /nullable compiler option [C#]
- -nullable compiler option [C#]
ms.openlocfilehash: 7454bb316507c3aaea208094127552712421dff6
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990122"
---
# <a name="-nullable-c-compiler-options"></a>-Nullable (opzioni del compilatore C#)

L'opzione **-Nullable** consente di specificare il contesto Nullable desiderato.

## <a name="syntax"></a>Sintassi

```console
-nullable[+ | -]
-nullable:{enable | disable | warnings | annotations}
```

## <a name="arguments"></a>Argomenti

`+` &#124; `-`  
Se `+` si specifica, o semplicemente **Nullable**, il compilatore Abilita il contesto Nullable. `-`Se si specifica, che è attivo se non si specifica **-Nullable**, Disabilita il contesto Nullable.

`enable`&#124; `disable` &#124; `warnings` &#124;`annotations`  
Specifica l'opzione di contesto Nullable. Simile a `+` o `-` , per abilitare e disabilitare, ma consente una maggiore granularità della specificità del contesto Nullable. L' `enable` argomento, che è attivo come se si specifica **-Nullable**, Abilita il contesto Nullable. Se `disable` si specifica, il contesto nullable viene disabilitato. Quando si specifica l' `warnings` argomento, **-Nullable: Warnings**, il contesto di avviso Nullable è abilitato. Quando si specifica l' `annotations` argomento **Nullable: Annotations**, il contesto dell'annotazione Nullable è abilitato.

## <a name="remarks"></a>Osservazioni

L'analisi del flusso viene utilizzata per dedurre il supporto dei valori Null delle variabili all'interno del codice eseguibile. Il supporto di valori null derivati di una variabile è indipendente dal supporto di valori null dichiarato della variabile. Le chiamate al metodo vengono analizzate anche quando vengono omesse in modo condizionale. Ad esempio, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> in modalità di rilascio.

La chiamata dei metodi annotati con gli attributi seguenti influirà anche sull'analisi del flusso:

- Condizioni preliminari semplici: <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute> e<xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute>
- Semplici post-condizioni: <xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute> e<xref:System.Diagnostics.CodeAnalysis.NotNullAttribute>
- Condizioni postali condizionali: <xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute> e<xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute>
- <xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute>(ad esempio, `DoesNotReturnIf(false)` per <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ) e<xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute>
- <xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute>
- Post-condizioni del membro: <xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String)> e<xref:System.Diagnostics.CodeAnalysis.MemberNotNullAttribute.%23ctor(System.String[])>

### <a name="to-set-this-compiler-option-in-a-project"></a>Per impostare questa opzione del compilatore in un progetto

Modificare il file con *estensione csproj* per aggiungere il `<Nullable>` tag all'interno di una `Project/PropertyGroup` gerarchia:

```xml
<Project Sdk="...">

  <PropertyGroup>
    <Nullable>enable</Nullable>
  </PropertyGroup>

</Project>
```

## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C#](./index.md)
- [Tipi riferimento nullable](../../nullable-references.md)
