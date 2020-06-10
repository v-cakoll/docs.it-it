---
title: Recupero di informazioni memorizzate negli attributi
description: Informazioni su come recuperare le informazioni archiviate negli attributi, ad esempio per un'istanza di attributo, molte istanze per lo stesso ambito, & molte istanze per ambiti diversi.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
ms.openlocfilehash: cf147a0ae6833039247c4c0878996973cc3db545
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "84661861"
---
# <a name="retrieving-information-stored-in-attributes"></a>Recupero di informazioni memorizzate negli attributi
Il recupero di un attributo personalizzato è un processo semplice. Dichiarare prima di tutto un'istanza dell'attributo da recuperare. Usare quindi il metodo <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> per inizializzare il nuovo attributo per il valore dell'attributo da recuperare. Dopo avere inizializzato il nuovo attributo, è sufficiente usarne le proprietà per ottenere i valori.  
  
> [!IMPORTANT]
> Questo argomento descrive come recuperare gli attributi personalizzati per il codice caricato nel contesto di esecuzione. Per recuperare gli attributi per il codice caricato nel contesto di sola reflection, è necessario usare la classe <xref:System.Reflection.CustomAttributeData>, come illustrato in [Procedura: Caricare assembly nel contesto Reflection-Only](../../framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 Questa sezione descrive i modi seguenti per recuperare gli attributi:  
  
- [Recupero di una singola istanza di un attributo](#cpconretrievingsingleinstanceofattribute)  
  
- [Recupero di più istanze di un attributo applicate allo stesso ambito](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
- [Recupero di più istanze di un attributo applicate a ambiti diversi](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Recupero di una singola istanza di un attributo  
 Nell'esempio seguente `DeveloperAttribute` (descritto nella sezione precedente) viene applicato alla classe `MainApp` a livello di classe. Il `GetAttribute` metodo usa **GetCustomAttribute** per recuperare i valori archiviati in `DeveloperAttribute` a livello di classe prima di visualizzarli nella console.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Questo programma visualizza il testo seguente quando viene eseguito.  
  
```console  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Se l'attributo non viene trovato, il metodo **GetCustomAttribute** inizializza `MyAttribute` per un valore null. Questo esempio cerca tale istanza in `MyAttribute` e informa l'utente se non vengono trovati attributi. Se `DeveloperAttribute` non viene trovato nell'ambito della classe, viene visualizzato il messaggio seguente nella console.  
  
```console  
The attribute was not found.
```  
  
 Questo esempio presuppone che la definizione dell'attributo sia nello spazio dei nomi corrente. Ricordare di importare lo spazio dei nomi in cui si trova la definizione dell'attributo se non è inclusa nello spazio dei nomi corrente.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Recupero di più istanze di un attributo applicate allo stesso ambito  
 Nell'esempio precedente la classe da analizzare e l'attributo specifico da trovare vengono passati a <xref:System.Attribute.GetCustomAttribute%2A>. Tale codice funziona correttamente solo se un'istanza di un attributo viene applicata a livello di classe. Se tuttavia più istanze di un attributo vengono applicate allo stesso livello di classe, il metodo **GetCustomAttribute** non recupera tutte le informazioni. Nei casi in cui più istanze dello stesso attributo vengono applicate allo stesso ambito, è possibile usare <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> per inserire tutte le istanze di un attributo in una matrice. Se ad esempio due istanze di `DeveloperAttribute` vengono applicate a livello di classe della stessa classe, il metodo `GetAttribute` può essere modificato per visualizzare le informazioni trovate in entrambi gli attributi. Si ricordi che, per applicare più attributi allo stesso livello, l'attributo deve essere definito con la proprietà **AllowMultiple** impostata su **true** in <xref:System.AttributeUsageAttribute>.  
  
 L'esempio di codice seguente illustra come usare il metodo **GetCustomAttributes** per creare una matrice che fa riferimento a tutte le istanze di `DeveloperAttribute` in una determinata classe. I valori di tutti gli attributi vengono quindi visualizzati nella console.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Se non vengono trovati attributi, questo codice avvisa l'utente. In caso contrario, vengono visualizzate le informazioni contenute in entrambe le istanze di `DeveloperAttribute`.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Recupero di più istanze di un attributo applicate ad ambiti diversi  
 I metodi <xref:System.Attribute.GetCustomAttributes%2A> e <xref:System.Attribute.GetCustomAttribute%2A> non eseguono la ricerca in un'intera classe e non restituiscono tutte le istanze di un attributo in tale classe. Cercano invece solo un metodo o membro specificato per volta. Se si ha una classe con lo stesso attributo applicato a ogni membro e si vogliono recuperare i valori in tutti gli attributi applicati a tali membri, è necessario fornire ogni metodo o membro singolarmente a **GetCustomAttributes** e ** GetCustomAttribute**.  
  
 L'esempio di codice seguente accetta una classe come parametro e cerca `DeveloperAttribute` (definito in precedenza) a livello di classe e in ogni singolo metodo di tale classe.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Se non vengono trovate istanze di `DeveloperAttribute` al livello di metodo o a livello di classe, il metodo `GetAttribute` notifica all'utente che non sono stati trovati attributi e visualizza il nome del metodo o della classe che non contiene l'attributo. Se viene trovato un attributo, i campi `Name`, `Level` e `Reviewed` vengono visualizzati nella console.  
  
 È possibile usare i membri della classe <xref:System.Type> per ottenere i singoli metodi e membri nella classe passata. Questo esempio esegue prima di tutto una query dell'oggetto **Type** per ottenere informazioni sugli attributi per il livello di classe. Usa quindi <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> per inserire le istanze di tutti i metodi in una matrice di oggetti <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> per recuperare informazioni sugli attributi per il livello di metodo. È anche possibile usare il metodo <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> per verificare la presenza di attributi a livello di proprietà o <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> per verificare la presenza di attributi a livello di costruttore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [Attributes (Attributi)](index.md)
