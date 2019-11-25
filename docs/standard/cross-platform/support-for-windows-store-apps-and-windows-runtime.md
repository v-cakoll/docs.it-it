---
title: Supporto .NET Framework per applicazioni Windows Store e Windows Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15d6262fb5e7dfb99759f0f85c9a197157713300
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204948"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Supporto .NET Framework per applicazioni Windows Store e Windows Runtime

The .NET Framework 4.5 supports a number of software development scenarios with the Windows Runtime. Questi scenari sono suddivisi in tre categorie:

- Developing Windows 8.x Store apps with XAML controls, as described in [Roadmap for Windows Store apps using C# or Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [How tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), and [.NET for Windows Store apps overview](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Developing class libraries to use in the Windows 8.x Store apps that you create with the .NET Framework.

- Developing Windows Runtime Components, packaged in .WinMD files, which can be used by any programming language that supports the Windows Runtime. For example, see [Creating Windows Runtime Components in C# and Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

This topic outlines the support that the .NET Framework provides for all three categories, and describes the scenarios for Windows Runtime Components. The first section includes basic information about the relationship between the .NET Framework and the Windows Runtime, and explains some oddities you might encounter in the Help system and the IDE. The [second section](#WindowsRuntimeComponents) discusses scenarios for developing Windows Runtime Components.

## <a name="the-basics"></a>Nozioni di base

The .NET Framework supports the three development scenarios listed earlier by providing [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], and by supporting the Windows Runtime itself.

- [.NET Framework and Windows Runtime namespaces](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) provides a streamlined view of the .NET Framework class libraries and include only the types and members you can use to create Windows 8.x Store apps and Windows Runtime Components.

  - When you use Visual Studio (Visual Studio 2012 or later) to develop a Windows 8.x Store app or a Windows Runtime component, a set of reference assemblies ensures that you see only the relevant types and members.

  - This streamlined API set is simplified further by the removal of features that are duplicated within the .NET Framework or that duplicate Windows Runtime features. For example, it contains only the generic versions of collection types, and the XML document object model is eliminated in favor of the Windows Runtime XML API set.

  - Features that simply wrap the operating system API are also removed, because the Windows Runtime is easy to call from managed code.

  To read more about the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], see the [.NET for Windows Store apps overview](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). To read about the API selection process, see the [.NET for Metro style apps](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) entry in the .NET blog.

- The [Windows Runtime](/uwp/api/) provides the user interface elements for building Windows 8.x Store apps, and provides access to operating system features. Like the .NET Framework, the Windows Runtime has metadata that enables the C# and Visual Basic compilers to use the Windows Runtime the way they use the .NET Framework class libraries. The .NET Framework makes it easier to use the Windows Runtime by hiding some differences:

  - Some differences in programming patterns between the .NET Framework and the Windows Runtime, such as the pattern for adding and removing event handlers, are hidden. È sufficiente usare il modello di .NET Framework.

  - Vengono celate alcune differenze nei tipi comunemente utilizzati, ad esempio i tipi primitivi e le raccolte. You simply use the .NET Framework type, as discussed in [Differences That Are Visible in the IDE](#DifferencesVisibleInIDE), later in this article.

Most of the time, .NET Framework support for the Windows Runtime is transparent. The next section discusses some of the apparent differences between managed code and the Windows Runtime.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>The .NET Framework and the Windows Runtime Reference Documentation

The Windows Runtime and the .NET Framework documentation sets are separate. Se si preme F1 per visualizzare la Guida su un tipo o un membro, viene visualizzata la documentazione di riferimento del set appropriato. However, if you browse through the [Windows Runtime reference](/uwp/api/) you might encounter examples that seem puzzling:

- Topics such as the <xref:Windows.Foundation.Collections.IIterable%601> interface don't have declaration syntax for Visual Basic or C#. Instead, a note appears above the syntax section (in this case, ".NET: This interface appears as System.Collections.Generic.IEnumerable\<T>"). This is because the .NET Framework and the Windows Runtime provide similar functionality with different interfaces. Inoltre, vi sono differenze di comportamento: `IIterable` dispone di un metodo `First` anziché di un metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> per restituire l'enumeratore. Instead of forcing you to learn a different way of performing a common task, the .NET Framework supports the Windows Runtime by making your managed code appear to use the type you're familiar with. You won't see the `IIterable` interface in the IDE, and therefore the only way you'll encounter it in the Windows Runtime reference documentation is by browsing through that documentation directly.

- The <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> documentation illustrates a closely related issue: Its parameter types appear to be different for different languages. Per C# e Visual Basic, i tipi di parametro sono <xref:System.String?displayProperty=nameWithType> e <xref:System.Uri?displayProperty=nameWithType>. Inoltre, questa situazione si verifica in quanto .NET Framework dispone di propri tipi `String` e `Uri` e, per questi tipi comunemente utilizzati, non ha senso imporre agli utenti di .NET Framework di apprendere un modo diverso per eseguire le operazioni. In the IDE, the .NET Framework hides the corresponding Windows Runtime types.

- In a few cases, such as the <xref:Windows.UI.Xaml.GridLength> structure, the .NET Framework provides a type with the same name but more functionality. Ad esempio, un set di argomenti su costruttori e proprietà è associato a `GridLength`, ma con blocchi di sintassi solo per Visual Basic e C# perché i membri sono disponibili solo nel codice gestito. In the Windows Runtime, structures have only fields. The Windows Runtime structure requires a helper class, <xref:Windows.UI.Xaml.GridLengthHelper>, to provide equivalent functionality. Non verrà visualizzata la classe di supporto nell'IDE quando si scrive il codice gestito.

- In the IDE, Windows Runtime types appear to derive from <xref:System.Object?displayProperty=nameWithType>. Sembrano disporre di membri ereditati da <xref:System.Object>, ad esempio <xref:System.Object.ToString%2A?displayProperty=nameWithType>. These members operate as they would if the types actually inherited from <xref:System.Object>, and Windows Runtime types can be cast to <xref:System.Object>. This functionality is part of the support that the .NET Framework provides for the Windows Runtime. However, if you view the types in the Windows Runtime reference documentation, no such members appear. La documentazione per questi membri apparentemente ereditati viene fornita dalla documentazione di riferimento a <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Differenze visibili nell'IDE

In more advanced programming scenarios, such as using a Windows Runtime component written in C# to provide the application logic for a Windows 8.x Store app built for Windows using JavaScript, such differences are apparent in the IDE as well as in the documentation. When your component returns an `IDictionary<int, string>` to JavaScript, and you look at it in the JavaScript debugger, you'll see the methods of `IMap<int, string>` because JavaScript uses the Windows Runtime type. Alcuni tipi di raccolte comunemente utilizzati che vengono visualizzati in modo diverso nei due linguaggi sono riportati nella tabella seguente:

|Tipo di Windows Runtime|Tipo .NET Framework corrispondente|
|--------------------------------------------------------------|---------------------------------------|
|`IIterable<T>`|`IEnumerable<T>`|
|`IIterator<T>`|`IEnumerator<T>`|
|`IVector<T>`|`IList<T>`|
|`IVectorView<T>`|`IReadOnlyList<T>`|
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|
|`IBindableIterable`|`IEnumerable`|
|`IBindableVector`|`IList`|
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|

In the Windows Runtime, `IMap<K, V>` and `IMapView<K, V>` are iterated using `IKeyValuePair`. Quando vengono passate al codice gestito, vengono visualizzate come `IDictionary<TKey, TValue>` e `IReadOnlyDictionary<TKey, TValue>`, ed è quindi naturale utilizzare `System.Collections.Generic.KeyValuePair<TKey, TValue>` per enumerarle.

Il modo in cui le interfacce vengono visualizzate nel codice gestito influisce sul modo in cui vengono visualizzati i tipi tramite cui vengono implementate queste interfacce. Ad esempio, tramite la classe `PropertySet` viene implementata l'interfaccia `IMap<K, V>`, che nel codice gestito viene visualizzata come `IDictionary<TKey, TValue>`. `PropertySet` compare come se avesse implementato `IDictionary<TKey, TValue>` anziché `IMap<K, V>`, dunque nel codice gestito risulta avere un metodo `Add` che si comporta come il metodo `Add` nei dizionari di .NET Framework. Non risulta avere un metodo `Insert`.

For more information about using the .NET Framework to create a Windows Runtime component, and a walkthrough that shows how to use such a component with JavaScript, see [Creating Windows Runtime Components in C# and Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipi primitivi

To enable the natural use of the Windows Runtime in managed code, .NET Framework primitive types appear instead of Windows Runtime primitive types in your code. In .NET Framework i tipi primitivi quali la struttura `Int32` presentano numerosi metodi e proprietà utili, ad esempio il metodo `Int32.TryParse`. By contrast, primitive types and structures in the Windows Runtime have only fields. Quando si utilizzano le primitive nel codice gestito, sembrano essere tipi .NET Framework e si possono utilizzare le proprietà e i metodi dei tipi .NET Framework normalmente. Nell'elenco seguente viene fornito un riepilogo:

- For the Windows Runtime primitives `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (an immutable collection of Unicode characters), `Enum`, `UInt32`, `UInt64`, and `Guid`, use the type of the same name in the `System` namespace.

- Per `UInt8`, utilizzare `System.Byte`.

- Per `Char16`, utilizzare `System.Char`.

- Per l'interfaccia `IInspectable`, utilizzare `System.Object`.

- Per `HRESULT`, utilizzare una struttura con un membro `System.Int32`.

As with interface types, the only time you might see evidence of this representation is when your .NET Framework project is a Windows Runtime component that is used by a Windows 8.x Store app built using JavaScript.

Other basic, commonly used Windows Runtime types that appear in managed code as their .NET Framework equivalents include the `Windows.Foundation.DateTime` structure, which appears in managed code as the <xref:System.DateTimeOffset?displayProperty=nameWithType> structure, and the `Windows.Foundation.TimeSpan` structure, which appears as the <xref:System.TimeSpan?displayProperty=nameWithType> structure.

### <a name="other-differences"></a>Altre differenze

In a few cases, the fact that .NET Framework types appear in your code instead of Windows Runtime types requires action on your part. For example, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in .NET Framework code. <xref:System.Uri?displayProperty=nameWithType> allows a relative URI, but <xref:Windows.Foundation.Uri?displayProperty=nameWithType> requires an absolute URI. Therefore, when you pass a URI to a Windows Runtime method, you must ensure that it's absolute. See [Passing a URI to the Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Scenari per lo sviluppo di componenti Windows Runtime

The scenarios that are supported for managed Windows Runtime Components depend on the following general principles:

- Windows Runtime Components that are built using the .NET Framework have no apparent differences from other Windows Runtimelibraries. For example, if you re-implement a native Windows Runtime component by using managed code, the two components are outwardly indistinguishable. Il fatto che il componente sia scritto in codice gestito non è visibile al codice in cui viene utilizzato, anche se il codice è esso stesso codice gestito. Tuttavia, internamente, il componente è realmente codice gestito e viene eseguito in Common Language Runtime (CLR).

- Components can contain types that implement application logic, Windows 8.x Store UI controls, or both.

  > [!NOTE]
  > È consigliabile separare gli elementi dell'interfaccia utente dalla logica dell'applicazione. Also, you can't use Windows 8.x Store UI controls in a Windows 8.x Store app built for Windows using JavaScript and HTML.

- A component can be a project within a Visual Studio solution for a Windows 8.x Store app, or a reusable component that you can add to multiple solutions.

  > [!NOTE]
  > If your component will be used only with C# or Visual Basic, there's no reason to make it a Windows Runtime component. If you make it an ordinary .NET Framework class library instead, you don't have to restrict its public API surface to Windows Runtime types.

- You can release versions of reusable components by using the Windows Runtime <xref:Windows.Foundation.Metadata.VersionAttribute> attribute to identify which types (and which members within a type) were added in different versions.

- The types in your component can derive from Windows Runtime types. Controls can derive from the primitive control types in the <xref:Windows.UI.Xaml.Controls.Primitives> namespace or from more finished controls such as <xref:Windows.UI.Xaml.Controls.Button>.

  > [!IMPORTANT]
  > Starting with [!INCLUDE[win8](../../../includes/win8-md.md)] and the .NET Framework 4.5, all public types in a managed Windows Runtime component must be sealed. A type in another Windows Runtime component can't derive from them. Se si desidera fornire il comportamento polimorfico nel componente, è possibile creare un'interfaccia e implementarla nei tipi polimorfici.

- All parameter and return types on the public types in your component must be Windows Runtime types (including the Windows Runtime types that your component defines).

Nelle sezioni seguenti vengono forniti esempi di scenari comuni.

### <a name="application-logic-for-a-windows-8x-store-app-with-javascript"></a>Application Logic for a Windows 8.x Store App with JavaScript

When you develop a Windows 8.x Store app for Windows using JavaScript, you might find that some parts of the application logic perform better in managed code, or are easier to develop. Con JavaScript non è possibile utilizzare direttamente le librerie di classi .NET Framework, ma si può rendere la libreria di classi un file con estensione WinMD. In this scenario, the Windows Runtime component is an integral part of the app, so it doesn't make sense to provide version attributes.

### <a name="reusable-windows-8x-store-ui-controls"></a>Reusable Windows 8.x Store UI Controls

You can package a set of related UI controls in a reusable Windows Runtime component. Il componente può essere commercializzato da solo o utilizzato come elemento nelle applicazioni create. In this scenario, it makes sense to use the Windows Runtime <xref:Windows.Foundation.Metadata.VersionAttribute> attribute to improve compatibility.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Logica di un'applicazione riutilizzabile da applicazioni .NET Framework esistenti

You can package managed code from your existing desktop apps as a standalone Windows Runtime component. This enables you to use the component in Windows 8.x Store apps built using C++ or JavaScript, as well as in Windows 8.x Store apps built using C# or Visual Basic. Il controllo delle versioni rappresenta un'opzione in caso di più scenari di riutilizzo del codice.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Panoramica di .NET per le app di Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Describes the .NET Framework types and members that you can use to create Windows 8.x Store apps and Windows RuntimeComponents. In Dev Center di Windows.|
|[Roadmap for Windows Store apps using C# or Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Provides key resources to help you get started developing Windows 8.x Store apps by using C# or Visual Basic, including many Quickstart topics, guidelines, and best practices. In Dev Center di Windows.|
|[How tos (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Provides key resources to help you get started developing Windows 8.x Store apps by using C# or Visual Basic, including many Quickstart topics, guidelines, and best practices. In Dev Center di Windows.|
|[Creazione di componenti Windows Runtime in C# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Describes how to create a Windows Runtime component using the .NET Framework, explains how to use it as part of a Windows 8.x Store app built for Windows using JavaScript, and describes how to debug the combination with Visual Studio. In Dev Center di Windows.|
|[Windows Runtime reference](/uwp/api/)|The reference documentation for the Windows Runtime. In Dev Center di Windows.|
|[Passaggio di un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Describes an issue that can arise when you pass a URI from managed code to the Windows Runtime, and how to avoid it.|
