---
title: 'Attributi riservati di C: Conditional, Obsolete, AttributeUsage'
ms.date: 04/09/2020
description: Questi attributi vengono interpretati dal compilatore per influire sul codice generato dal compilatore
ms.openlocfilehash: ca3b76387de2a57380d6eb0848991d979a558662
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389870"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a>Attributi riservati: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute

Questi attributi possono essere applicati agli elementi nel codice. Aggiungono significato semantico a tali elementi. Il compilatore utilizza tali significati semantici per modificarne l'output e segnalare i possibili errori degli sviluppatori che utilizzano il codice.

## <a name="conditional-attribute"></a>Attributo `Conditional`

L'attributo `Conditional` rende l'esecuzione di un metodo dipendente da un identificatore di pre-elaborazione. L'attributo `Conditional` è un alias per <xref:System.Diagnostics.ConditionalAttribute> e può essere applicato a un metodo o a una classe Attribute.

Nell'esempio seguente, `Conditional` viene applicato a un metodo per abilitare o disabilitare la visualizzazione di informazioni diagnostiche specifiche del programma:

::::::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

Se `TRACE_ON` l'identificatore non è definito, l'output di traccia non viene visualizzato. Esplora tu stesso nella finestra interattiva.

L'attributo `Conditional` viene `DEBUG` spesso utilizzato con l'identificatore per abilitare le funzionalità di traccia e registrazione per le build di debug, ma non nelle build di rilascio, come illustrato nell'esempio seguente:The attribute is often used with the identifier to enable trace and logging features for debug builds but not in release builds, as shown in the following example:

::::::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

Quando viene chiamato un metodo contrassegnato come condizionale, la presenza o l'assenza del simbolo di pre-elaborazione specificato determina se la chiamata viene inclusa o omessa. Se il simbolo è definito la chiamata viene inclusa, in caso contrario viene omessa. Un metodo condizionale deve essere un metodo in una `void` dichiarazione di classe o struct e deve avere un tipo restituito. L'uso `Conditional` è più pulito, più elegante e meno `#if…#endif` soggetto a errori rispetto ai metodi di inclusione all'interno dei blocchi.

Se un metodo `Conditional` ha più attributi, una chiamata al metodo viene inclusa se in uno o più simboli condizionali sono definiti (i simboli sono collegati logicamente tra loro utilizzando l'operatore OR). Nell'esempio seguente, la `A` presenza `B` di uno o restituisce una chiamata al metodo:In the following example, the presence of either or results in a method call:

::::::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a>Utilizzo `Conditional` con le classi di attributiUsing with attribute classes

L'attributo `Conditional` può essere applicato anche a una definizione di classe Attribute. Nell'esempio seguente, l'attributo `Documentation` personalizzato aggiungerà `DEBUG` informazioni ai metadati solo se è definito.

::::::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a>Attributo `Obsolete`

L'attributo `Obsolete` contrassegna un elemento di codice come non più consigliato per l'utilizzo. L'utilizzo di un'entità contrassegnata come obsoleta genera un avviso o un errore. `Obsolete` è un attributo monouso e può essere applicato a qualsiasi entità che supporta gli attributi. `Obsolete` è un alias per <xref:System.ObsoleteAttribute>.

Nell'esempio riportato di seguito l'attributo `Obsolete` viene applicato alla classe `A` e al metodo `B.OldMethod`. Poiché il secondo argomento del costruttore dell'attributo applicato a `B.OldMethod` è impostato su `true` questo metodo genererà un errore del compilatore, mentre l'uso della classe `A` produrrà semplicemente un avviso. Tuttavia la chiamata di `B.NewMethod` non produrrà né un avviso né un errore. Ad esempio, se viene usato con le definizioni precedenti, il codice che segue genera due avvisi e un errore:

::::::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

La stringa fornita come primo argomento per il costruttore dell'attributo verrà visualizzata come parte dell'avviso o dell'errore. Vengono generati due avvisi per la classe `A`: uno per la dichiarazione del riferimento alla classe e uno per il costruttore della classe. L'attributo `Obsolete` può essere utilizzato senza argomenti, ma è consigliabile includere una spiegazione di cosa usare.

## <a name="attributeusage-attribute"></a>Attributo `AttributeUsage`

L'attributo `AttributeUsage` determina la modalità di utilizzo di una classe di attributi personalizzati. <xref:System.AttributeUsageAttribute> è un attributo che si applica alle definizioni di attributi personalizzati. L'attributo `AttributeUsage` consente di controllare:

- Elementi del programma a cui l'attributo può essere applicato. Se non se ne limita l'utilizzo, un attributo può essere applicato a uno qualsiasi degli elementi del programma seguenti:
  - assembly
  - modulo
  - campo
  - event
  - method
  - param
  - proprietà
  - return
  - type
- Se un attributo può essere applicato più volte a un singolo elemento del programma.
- Se gli attributi vengono ereditati dalle classi derivate.

Le impostazioni predefinite sono simili all'esempio seguente quando vengono applicate in modo esplicito:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

In questo esempio la classe `NewAttribute` può essere applicata a qualsiasi elemento del programma supportato, ma solo una volta a ogni entità. L'attributo viene ereditato dalle classi derivate se applicato a una classe base.

Gli argomenti <xref:System.AttributeUsageAttribute.AllowMultiple> e <xref:System.AttributeUsageAttribute.Inherited> sono facoltativi, quindi il codice seguente ha lo stesso effetto:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

Il primo argomento <xref:System.AttributeUsageAttribute> deve consistere di uno o più elementi dell'enumerazione <xref:System.AttributeTargets>. Più tipi di destinazione possono essere collegati con l'operatore OR, nel modo illustrato nell'esempio seguente:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

A partire da C# 7.3, gli attributi possono essere applicati alla proprietà o al campo sottostante per una proprietà implementata automaticamente. L'attributo si applica alla proprietà, a meno che non si specifichi l'identificatore `field` per l'attributo. Entrambe le situazioni sono illustrate nell'esempio seguente:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

Se l'argomento <xref:System.AttributeUsageAttribute.AllowMultiple> è `true`, l'attributo restituito può essere applicato più volte a una singola entità, come illustrato nell'esempio seguente:

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

In questo caso, `MultiUseAttribute` può essere applicato più volte perché `AllowMultiple` è impostato su `true`. Entrambi i formati illustrati per applicare più attributi sono validi.

Se <xref:System.AttributeUsageAttribute.Inherited> è `false`, l'attributo non viene ereditato dalle classi derivate da una classe con attributi. Ad esempio:

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

In questo caso `NonInheritedAttribute` non viene applicato a `DClass` attraverso l'ereditarietà.

## <a name="see-also"></a>Vedere anche

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Attributi](../../../standard/attributes/index.md)
- [Reflection](../../programming-guide/concepts/reflection.md)
