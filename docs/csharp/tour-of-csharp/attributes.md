---
title: Attributi C# - Panoramica del linguaggio C#
description: Informazioni sulla programmazione dichiarativa con attributi in C#
ms.date: 08/10/2016
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: 671023f268ae78d63db8868ef6046b8f13880659
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312235"
---
# <a name="attributes"></a>Attributi

Tipi, membri e altre entità di un programma C# supportano modificatori che controllano alcuni aspetti del loro comportamento. L'accessibilità di un metodo, ad esempio, è controllata con i modificatori `public`, `protected`, `internal` e `private`. Il linguaggio C# generalizza questa funzionalità in modo che i tipi di informazioni dichiarative definiti dall'utente possano essere associati a entità di programma e recuperati in fase di esecuzione. I programmi specificano queste informazioni dichiarative aggiuntive definendo e usando ***attributi***.

Nell'esempio seguente viene dichiarato un attributo `HelpAttribute` che può essere inserito in entità di programma per fornire collegamenti alla documentazione correlata.

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

Tutte le classi di attributo derivano dalla classe di base <xref:System.Attribute> fornita dalla libreria standard. Gli attributi possono essere applicati specificandone il nome (con eventuali argomenti) tra parentesi quadre appena prima della dichiarazione associata. Se il nome dell'attributo termina con `Attribute`, questa parte del nome può essere omessa quando si fa riferimento all'attributo. Ad esempio, è possibile usare `HelpAttribute` come segue.

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

In questo esempio viene associato un attributo `HelpAttribute` alla classe `Widget` e viene aggiunto un altro attributo `HelpAttribute` al metodo `Display` nella classe. I costruttori pubblici di una classe di attributo controllano le informazioni che devono essere specificate quando l'attributo è associato a un'entità di programma. È possibile specificare informazioni aggiuntive facendo riferimento a proprietà di lettura/scrittura pubbliche della classe di attributo, ad esempio il riferimento alla proprietà `Topic` precedente.

Se un attributo viene richiesto tramite reflection, il costruttore della classe di attributo viene richiamato con le informazioni specificate nell'origine del programma e viene restituita l'istanza dell'attributo risultante. Se sono state fornite informazioni aggiuntive tramite proprietà, queste vengono impostate sui valori specificati prima che venga restituita l'istanza dell'attributo.

>[!div class="step-by-step"]
[Precedente](delegates.md)
