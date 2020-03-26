---
title: "Procedura: controllare il contenuto dell'assembly tramite MetadataLoadContextHow to: Inspect assembly contents using MetadataLoadContext"
description: Informazioni su come usare MetadataLoadContext, un'API che consente di caricare assembly .NET a scopo di ispezione.
author: MSDN-WhiteKnight
ms.date: 03/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: a782b2db4fb62cfaedaa6768e2131bda6bec864c
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80229301"
---
# <a name="how-to-inspect-assembly-contents-using-metadataloadcontext"></a>Procedura: controllare il contenuto dell'assembly tramite MetadataLoadContextHow to: Inspect assembly contents using MetadataLoadContext

L'API di reflection in .NET per impostazione predefinita consente agli sviluppatori di esaminare il contenuto degli assembly caricati nel contesto di esecuzione principale. Tuttavia, a volte non è possibile caricare un assembly nel contesto di esecuzione, ad esempio perché è stato compilato per un'altra piattaforma o architettura del processore o è un assembly di [riferimento.](reference-assemblies.md) L'API <xref:System.Reflection.MetadataLoadContext?displayProperty=fullName> consente di caricare e controllare tali assembly. Gli assembly <xref:System.Reflection.MetadataLoadContext> caricati in vengono trattati solo come metadati, ovvero è possibile esaminare i tipi nell'assembly, ma non è possibile eseguire il codice in esso contenuto. A differenza del contesto di esecuzione principale, l'oggetto <xref:System.Reflection.MetadataLoadContext> non carica automaticamente le dipendenze dalla directory corrente; utilizza invece la logica di <xref:System.Reflection.MetadataAssemblyResolver> associazione personalizzata fornita dal passato a esso.

## <a name="prerequisites"></a>Prerequisiti

Per <xref:System.Reflection.MetadataLoadContext>utilizzare , installare il pacchetto [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) NuGet. È supportato in qualsiasi framework di destinazione conforme a .NET Standard 2.0, ad esempio .NET Core 2.0 o .NET Framework 4.6.1.

## <a name="create-metadataassemblyresolver-for-metadataloadcontext"></a>Creare MetadataAssemblyResolver per MetadataLoadContextCreate MetadataAssemblyResolver for MetadataLoadContext

La <xref:System.Reflection.MetadataLoadContext> creazione di è <xref:System.Reflection.MetadataAssemblyResolver>necessario fornire l'istanza del file . Il modo più semplice per <xref:System.Reflection.PathAssemblyResolver>fornirne uno consiste nell'utilizzare l'oggetto , che risolve gli assembly dalla raccolta specificata di stringhe del percorso di assembly. Questa raccolta, oltre agli assembly che si desidera esaminare direttamente, deve includere anche tutte le dipendenze necessarie. Ad esempio, per leggere l'attributo personalizzato che si trova in un assembly esterno, è necessario includere tale assembly o verrà generata un'eccezione. Nella maggior parte dei casi, è necessario includere almeno l'assembly *di base,* ovvero l'assembly contenente i tipi di sistema incorporati, ad <xref:System.Object?displayProperty=nameWithType>esempio . Il codice seguente viene <xref:System.Reflection.PathAssemblyResolver> illustrato come creare l'utilizzando la raccolta costituita dall'assembly controllato e l'assembly principale del runtime corrente:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CoreAssembly)]

Se è necessario accedere a tutti i tipi BCL, è possibile includere tutti gli assembly di runtime nella raccolta. Nel codice seguente viene <xref:System.Reflection.PathAssemblyResolver> illustrato come creare l'oggetto utilizzando la raccolta costituita dall'assembly controllato e da tutti gli assembly del runtime corrente:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#RuntimeAssemblies)]

## <a name="create-metadataloadcontext"></a>Creare MetadataLoadContextCreate MetadataLoadContext

Per creare <xref:System.Reflection.MetadataLoadContext>l'oggetto <xref:System.Reflection.MetadataLoadContext.%23ctor%28System.Reflection.MetadataAssemblyResolver%2CSystem.String%29>, richiamare <xref:System.Reflection.MetadataAssemblyResolver> il relativo costruttore , passando il parametro creato in precedenza come primo parametro e il nome dell'assembly di base come secondo parametro. È possibile omettere il nome dell'assembly principale, nel qual caso il costruttore tenterà di utilizzare i nomi predefiniti: "mscorlib", "System.Runtime" o "netstandard".

Dopo aver creato il contesto, è possibile caricare <xref:System.Reflection.MetadataLoadContext.LoadFromAssemblyPath%2A>gli assembly in esso utilizzando metodi quali . È possibile usare tutte le API di reflection negli assembly caricati, ad eccezione di quelli che implicano l'esecuzione del codice. Il <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A> metodo prevede l'esecuzione di costruttori, pertanto utilizzare il <xref:System.Reflection.MemberInfo.GetCustomAttributesData%2A> metodo <xref:System.Reflection.MetadataLoadContext>quando è necessario esaminare gli attributi personalizzati nell'oggetto .

Nell'esempio di <xref:System.Reflection.MetadataLoadContext>codice riportato di seguito viene creato , l'assembly viene caricato in esso e gli attributi dell'assembly vengono restituiti nella console:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CreateContext)]

## <a name="example"></a>Esempio

Per un esempio di codice completo, consultate [Esaminare il contenuto dell'assembly tramite MetadataLoadContext](https://docs.microsoft.com/samples/dotnet/samples/inspect-assembly-contents-using-metadataloadcontext/).
