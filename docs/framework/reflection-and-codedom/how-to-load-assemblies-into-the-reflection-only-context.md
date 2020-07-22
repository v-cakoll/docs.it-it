---
title: 'Procedura: Caricare assembly nel contesto Reflection-Only'
description: Vedere un esempio di come caricare gli assembly nel contesto di sola reflection in .NET. Esaminare gli assembly compilati per altre piattaforme o versioni .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: 92f847f6c61ba39bf8621af6080baccfdabe514a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865073"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a>Procedura: Caricare assembly nel contesto Reflection-Only

Il contesto di caricamento di sola reflection consente di esaminare gli assembly compilati per altre piattaforme o altre versioni di .NET Framework. Il codice caricato in questo contesto può essere solo esaminato e non eseguito. Di conseguenza, poiché i costruttori non possono essere eseguiti, non è possibile creare oggetti. Non essendo possibile eseguire il codice, le dipendenze non vengono caricate automaticamente. Per esaminarle, è necessario caricarle manualmente.

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a>Per caricare un assembly nel contesto di caricamento di sola reflection

1. Usare l'overload del metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> per caricare l'assembly in base al nome di visualizzazione oppure il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> per caricare l'assembly in base al percorso. Se l'assembly è un'immagine binaria, usare l'overload del metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>.

    > [!NOTE]
    > Non è possibile usare il contesto di sola reflection per caricare una versione di mscorlib.dll da una versione di .NET Framework diversa da quella installata nel contesto di esecuzione.

2. Se l'assembly contiene dipendenze, queste ultime non verranno caricate dal metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>. Per esaminarle, è necessario caricarle manualmente.

3. Determinare se un assembly viene caricato nel contesto di sola reflection usando la proprietà <xref:System.Reflection.Assembly.ReflectionOnly%2A> dell'assembly.

4. Se all'assembly o ai tipi in esso contenuti sono applicati attributi, esaminare gli attributi usando la classe <xref:System.Reflection.CustomAttributeData> per assicurarsi che non venga effettuato alcun tentativo di eseguire il codice nel contesto di sola reflection. Usare l'overload appropriato del metodo <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> per ottenere gli oggetti <xref:System.Reflection.CustomAttributeData> che rappresentano gli attributi applicati a un assembly, membro, modulo o parametro.

    > [!NOTE]
    > Gli attributi applicati all'assembly o al relativo contenuto possono essere definiti nell'assembly o in un altro assembly caricato nel contesto di sola reflection. Non è possibile stabilire in anticipo dove sono definiti gli attributi.

## <a name="example"></a>Esempio

L'esempio di codice seguente illustra come esaminare gli attributi applicati a un assembly caricato nel contesto di sola reflection.

L'esempio di codice definisce un attributo personalizzato con due costruttori e una proprietà. L'attributo è applicato all'assembly, a un tipo dichiarato nell'assembly, a un metodo del tipo e a un parametro del metodo. Quando viene eseguito, l'assembly viene caricato nel contesto di sola reflection e vengono visualizzate informazioni sugli attributi personalizzati applicati all'assembly e ai tipi e membri che contiene.

> [!NOTE]
> Per semplificare l'esempio di codice, l'assembly carica ed esamina se stesso. In genere, non è probabile che lo stesso assembly venga caricato sia nel contesto di esecuzione che nel contesto di sola reflection.

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
