---
title: Attributi C# - Panoramica del linguaggio C#
description: Informazioni sulla programmazione dichiarativa con attributi in C#
keywords: .NET, csharp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: 6878a408ef892ee47a03bfa04f736b9bf9671696
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2017
---
# <a name="attributes"></a><span data-ttu-id="fdd1e-104">Attributi</span><span class="sxs-lookup"><span data-stu-id="fdd1e-104">Attributes</span></span>

<span data-ttu-id="fdd1e-105">Tipi, membri e altre entità di un programma C# supportano modificatori che controllano alcuni aspetti del loro comportamento.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-105">Types, members, and other entities in a C# program support modifiers that control certain aspects of their behavior.</span></span> <span data-ttu-id="fdd1e-106">L'accessibilità di un metodo, ad esempio, è controllata con i modificatori `public`, `protected`, `internal` e `private`.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-106">For example, the accessibility of a method is controlled using the `public`, `protected`, `internal`, and `private` modifiers.</span></span> <span data-ttu-id="fdd1e-107">Il linguaggio C# generalizza questa funzionalità in modo che i tipi di informazioni dichiarative definiti dall'utente possano essere associati a entità di programma e recuperati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-107">C# generalizes this capability such that user-defined types of declarative information can be attached to program entities and retrieved at run-time.</span></span> <span data-ttu-id="fdd1e-108">I programmi specificano queste informazioni dichiarative aggiuntive definendo e usando ***attributi***.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-108">Programs specify this additional declarative information by defining and using ***attributes***.</span></span>

<span data-ttu-id="fdd1e-109">Nell'esempio seguente viene dichiarato un attributo `HelpAttribute` che può essere inserito in entità di programma per fornire collegamenti alla documentazione correlata.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-109">The following example declares a `HelpAttribute` attribute that can be placed on program entities to provide links to their associated documentation.</span></span>

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

<span data-ttu-id="fdd1e-110">Tutte le classi di attributo derivano dalla classe di base <xref:System.Attribute> fornita dalla libreria standard.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-110">All attribute classes derive from the <xref:System.Attribute> base class provided by the standard library.</span></span> <span data-ttu-id="fdd1e-111">Gli attributi possono essere applicati specificandone il nome (con eventuali argomenti) tra parentesi quadre appena prima della dichiarazione associata.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-111">Attributes can be applied by giving their name, along with any arguments, inside square brackets just before the associated declaration.</span></span> <span data-ttu-id="fdd1e-112">Se il nome dell'attributo termina con `Attribute`, questa parte del nome può essere omessa quando si fa riferimento all'attributo.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-112">If an attribute’s name ends in `Attribute`, that part of the name can be omitted when the attribute is referenced.</span></span> <span data-ttu-id="fdd1e-113">L'attributo `HelpAttribute`, ad esempio, può essere usato come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-113">For example, the `HelpAttribute` attribute can be used as follows.</span></span>

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

<span data-ttu-id="fdd1e-114">In questo esempio viene associato un attributo `HelpAttribute` alla classe `Widget`</span><span class="sxs-lookup"><span data-stu-id="fdd1e-114">This example attaches a `HelpAttribute` to the `Widget` class.</span></span> <span data-ttu-id="fdd1e-115">e viene aggiunto un altro attributo `HelpAttribute` al metodo `Display` nella classe.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-115">It adds another `HelpAttribute` to the `Display` method in the class.</span></span> <span data-ttu-id="fdd1e-116">I costruttori pubblici di una classe di attributo controllano le informazioni che devono essere specificate quando l'attributo è associato a un'entità di programma.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-116">The public constructors of an attribute class control the information that must be provided when the attribute is attached to a program entity.</span></span> <span data-ttu-id="fdd1e-117">È possibile specificare informazioni aggiuntive facendo riferimento a proprietà di lettura/scrittura pubbliche della classe di attributo, ad esempio il riferimento alla proprietà `Topic` precedente.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-117">Additional information can be provided by referencing public read-write properties of the attribute class (such as the reference to the `Topic` property previously).</span></span>

<span data-ttu-id="fdd1e-118">Se un attributo viene richiesto tramite reflection, il costruttore della classe di attributo viene richiamato con le informazioni specificate nell'origine del programma e viene restituita l'istanza dell'attributo risultante.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-118">When a particular attribute is requested through reflection, the constructor for the attribute class is invoked with the information provided in the program source, and the resulting attribute instance is returned.</span></span> <span data-ttu-id="fdd1e-119">Se sono state fornite informazioni aggiuntive tramite proprietà, queste vengono impostate sui valori specificati prima che venga restituita l'istanza dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="fdd1e-119">If additional information was provided through properties, those properties are set to the given values before the attribute instance is returned.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="fdd1e-120">Precedente</span><span class="sxs-lookup"><span data-stu-id="fdd1e-120">Previous</span></span>](delegates.md)
