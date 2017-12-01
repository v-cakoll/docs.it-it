---
title: Recupero di informazioni memorizzate negli attributi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a>Recupero di informazioni memorizzate negli attributi
Il recupero di un attributo personalizzato è un processo semplice. Innanzitutto, dichiarare un'istanza dell'attributo da recuperare. Utilizzare quindi la <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> metodo per inizializzare il nuovo attributo per il valore dell'attributo da recuperare. Una volta che viene inizializzato il nuovo attributo, utilizzare semplicemente le proprietà per ottenere i valori.  
  
> [!IMPORTANT]
>  In questo argomento viene descritto come recuperare gli attributi per il codice caricato nel contesto di esecuzione. Per recuperare gli attributi per il codice caricato nel contesto reflection-only, è necessario utilizzare il <xref:System.Reflection.CustomAttributeData> classe, come illustrato nella [come: caricamento di assembly nel contesto di only](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 In questa sezione vengono descritti i modi per recuperare gli attributi seguenti:  
  
-   [Recupero di una singola istanza di un attributo](#cpconretrievingsingleinstanceofattribute)  
  
-   [Recupero di più istanze di un attributo applicate allo stesso ambito](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Recupero di più istanze di un attributo applicato a diversi ambiti](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Recupero di una singola istanza di un attributo  
 Nell'esempio seguente, il `DeveloperAttribute` (descritto nella sezione precedente) viene applicato per la `MainApp` il livello di classe. Il `GetAttribute` metodo utilizza **GetCustomAttribute** per recuperare i valori archiviati in `DeveloperAttribute` a livello di classe prima di visualizzarli nella console.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Questo programma consente di visualizzare il testo seguente, quando eseguita.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Se l'attributo non viene trovato, il **GetCustomAttribute** metodo inizializza `MyAttribute` su un valore null. Questo esempio viene verificata `MyAttribute` per tale istanza e l'utente viene informato se viene trovato alcun attributo. Se il `DeveloperAttribute` non viene trovato nell'ambito della classe, viene visualizzato il messaggio seguente nella console.  
  
```  
The attribute was not found.   
```  
  
 Questo esempio si presuppone che la definizione dell'attributo è nello spazio dei nomi corrente. È necessario importare lo spazio dei nomi in cui si trova la definizione dell'attributo se non è incluso nello spazio dei nomi corrente.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Recupero di più istanze di un attributo applicate allo stesso ambito  
 Nell'esempio precedente, la classe da analizzare e l'attributo specifico da trovare vengono passati a <xref:System.Attribute.GetCustomAttribute%2A>. Il codice funziona correttamente solo se un'istanza di un attributo viene applicata a livello di classe. Tuttavia, se più istanze di un attributo vengono applicate allo stesso livello di classe, il **GetCustomAttribute** metodo non recupera tutte le informazioni. Nei casi in cui più istanze dello stesso attributo vengono applicate allo stesso ambito, è possibile utilizzare <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> a inserire tutte le istanze di un attributo in una matrice. Ad esempio, se due istanze di `DeveloperAttribute` vengono applicate a livello di classe della stessa classe, il `GetAttribute` metodo può essere modificato per visualizzare le informazioni presenti in entrambi gli attributi. Per applicare più attributi allo stesso livello, l'attributo deve essere definito con il **AllowMultiple** proprietà impostata su **true** nel <xref:System.AttributeUsageAttribute>.  
  
 Esempio di codice seguente viene illustrato come utilizzare il **GetCustomAttributes** metodo per creare una matrice che fa riferimento a tutte le istanze di `DeveloperAttribute` in una classe specificata. I valori di tutti gli attributi vengono quindi visualizzati nella console.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Se viene trovato alcun attributo, questo codice avvisa l'utente. In caso contrario, le informazioni contenute in entrambe le istanze di `DeveloperAttribute` viene visualizzato.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Recupero di più istanze di un attributo applicato a diversi ambiti  
 Il <xref:System.Attribute.GetCustomAttributes%2A> e <xref:System.Attribute.GetCustomAttribute%2A> metodi non cercare un'intera classe e restituire tutte le istanze di un attributo in tale classe. Invece, la ricerca solo un metodo o un membro alla volta. Se si dispone di una classe con lo stesso attributo applicato a ogni membro e si desidera recuperare i valori in tutti gli attributi applicati ai membri, deve fornire singolarmente a ogni metodo o membro **GetCustomAttributes** e  **GetCustomAttribute**.  
  
 Esempio di codice seguente accetta una classe come parametro e cerca il `DeveloperAttribute` , definita in precedenza, a livello di classe e per ogni singolo metodo di tale classe.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Se nessuna istanza del `DeveloperAttribute` presenti nel livello di metodo o il livello di classe, il `GetAttribute` metodo notifica all'utente che non sono stati trovati attributi e visualizza il nome del metodo o della classe che contiene l'attributo. Se viene trovato un attributo, il `Name`, `Level`, e `Reviewed` i campi vengono visualizzati nella console.  
  
 È possibile utilizzare i membri del <xref:System.Type> classe per ottenere i singoli metodi e i membri della classe passata. In questo esempio viene innanzitutto eseguita una query di **tipo** oggetto per cui ottenere informazioni sugli attributi per il livello di classe. Viene quindi utilizzato <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> per inserire le istanze di tutti i metodi in una matrice di <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> oggetti da recuperare informazioni sugli attributi per il livello di metodo. È inoltre possibile utilizzare il <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> metodo per verificare la presenza di attributi a livello di proprietà o <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> per verificare la presenza di attributi a livello di costruttore.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [Attributi](../../../docs/standard/attributes/index.md)
