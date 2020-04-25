---
title: "Procedura: controllare il contenuto dell'assembly tramite MetadataLoadContext"
description: Informazioni su come usare MetadataLoadContext, un'API che consente di caricare assembly .NET a scopo di controllo.
author: MSDN-WhiteKnight
ms.date: 03/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 90c84147c52199afc42a2efc297bc7fe40658ec7
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141193"
---
# <a name="how-to-inspect-assembly-contents-using-metadataloadcontext"></a>Procedura: controllare il contenuto dell'assembly tramite MetadataLoadContext

Per impostazione predefinita, l'API Reflection in .NET consente agli sviluppatori di ispezionare il contenuto degli assembly caricati nel contesto di esecuzione principale. Tuttavia, a volte non è possibile caricare un assembly nel contesto di esecuzione, ad esempio perché è stato compilato per un'altra architettura di piattaforma o processore oppure è un [assembly di riferimento](reference-assemblies.md). L' <xref:System.Reflection.MetadataLoadContext?displayProperty=fullName> API consente di caricare e ispezionare tali assembly. Gli <xref:System.Reflection.MetadataLoadContext> assembly caricati in vengono considerati solo come metadati, ovvero è possibile esaminare i tipi nell'assembly, ma non è possibile eseguire alcun codice contenuto. A differenza del contesto di esecuzione principale, <xref:System.Reflection.MetadataLoadContext> non carica automaticamente le dipendenze dalla directory corrente. USA invece la logica di binding personalizzata fornita dall'oggetto <xref:System.Reflection.MetadataAssemblyResolver> passato.

## <a name="prerequisites"></a>Prerequisiti

Per usare <xref:System.Reflection.MetadataLoadContext>, installare il pacchetto NuGet [System. Reflection. MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) . È supportato in qualsiasi framework di destinazione conforme a .NET Standard 2,0, ad esempio .NET Core 2,0 o .NET Framework 4.6.1.

## <a name="create-metadataassemblyresolver-for-metadataloadcontext"></a>Creare MetadataAssemblyResolver per MetadataLoadContext

Per creare <xref:System.Reflection.MetadataLoadContext> l'oggetto è necessario fornire l' <xref:System.Reflection.MetadataAssemblyResolver>istanza di. Il modo più semplice per fornirne uno consiste nell'usare <xref:System.Reflection.PathAssemblyResolver>, che risolve gli assembly dalla raccolta specificata di stringhe di percorso dell'assembly. Questa raccolta, oltre agli assembly che si desidera esaminare direttamente, deve includere anche tutte le dipendenze necessarie. Ad esempio, per leggere l'attributo personalizzato che si trova in un assembly esterno, è necessario includere tale assembly o verrà generata un'eccezione. Nella maggior parte dei casi, è necessario includere almeno l' *assembly principale*, ovvero l'assembly contenente i tipi di sistema predefiniti, ad esempio <xref:System.Object?displayProperty=nameWithType>. Il codice seguente illustra come creare <xref:System.Reflection.PathAssemblyResolver> usando la raccolta costituita dall'assembly ispezionato e dall'assembly principale del runtime corrente:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CoreAssembly)]

Se è necessario accedere a tutti i tipi di BCL, è possibile includere tutti gli assembly di runtime nella raccolta. Nel codice seguente viene illustrato come creare l' <xref:System.Reflection.PathAssemblyResolver> oggetto utilizzando la raccolta costituita dall'assembly ispezionato e da tutti gli assembly del runtime corrente:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#RuntimeAssemblies)]

## <a name="create-metadataloadcontext"></a>Crea MetadataLoadContext

Per creare <xref:System.Reflection.MetadataLoadContext>, richiamare il relativo costruttore <xref:System.Reflection.MetadataLoadContext.%23ctor%28System.Reflection.MetadataAssemblyResolver%2CSystem.String%29>, passando l'oggetto creato <xref:System.Reflection.MetadataAssemblyResolver> in precedenza come primo parametro e il nome dell'assembly principale come secondo parametro. È possibile omettere il nome dell'assembly principale, nel qual caso il costruttore tenterà di usare i nomi predefiniti: "mscorlib", "System. Runtime" o "netstandard".

Dopo aver creato il contesto, è possibile caricarvi assembly usando metodi quali <xref:System.Reflection.MetadataLoadContext.LoadFromAssemblyPath%2A>. È possibile usare tutte le API di Reflection negli assembly caricati ad eccezione di quelle che coinvolgono l'esecuzione del codice. Il <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A> metodo comporta l'esecuzione dei costruttori <xref:System.Reflection.MemberInfo.GetCustomAttributesData%2A> <xref:System.Reflection.MetadataLoadContext>. utilizzare invece il metodo quando è necessario esaminare gli attributi personalizzati in.

Nell'esempio di codice seguente <xref:System.Reflection.MetadataLoadContext>viene creato, caricato l'assembly e vengono restituiti gli attributi di assembly nella console:

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CreateContext)]

## <a name="example"></a>Esempio

Per un esempio di codice completo, vedere l' [esempio esaminare il contenuto dell'assembly usando MetadataLoadContext](https://docs.microsoft.com/samples/dotnet/samples/inspect-assembly-contents-using-metadataloadcontext/).
