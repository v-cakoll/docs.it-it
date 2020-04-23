---
title: Visualizzazione delle informazioni sul tipo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
ms.openlocfilehash: bf119ff547df59cd369d688fd81ab058893614f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130021"
---
# <a name="viewing-type-information"></a>Visualizzazione delle informazioni sul tipo
La classe <xref:System.Type?displayProperty=nameWithType> è fondamentale per la reflection. Quando la reflection lo richiede, Common Language Runtime crea l'oggetto **Type** relativo a un tipo caricato. Per ottenere informazioni sul tipo, è possibile usare metodi, campi, proprietà e classi nidificate dell'oggetto **Type**.  
  
 Usare <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> per ottenere oggetti **Type** da assembly che non sono stati caricati, passando il nome del tipo o dei tipi desiderati. Usare <xref:System.Type.GetType%2A?displayProperty=nameWithType> per ottenere oggetti **Type** da un assembly già caricato. Usare <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> e <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> per ottenere gli oggetti **Type** dei moduli.  
  
> [!NOTE]
> Se si vuole esaminare e modificare tipi e metodi generici, vedere le altre informazioni disponibili in [Reflection e tipi generici](reflection-and-generic-types.md) e [Procedura: Esaminare e creare istanze di tipi generici tramite reflection](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 L'esempio seguente illustra la sintassi necessaria per ottenere il modulo e l'oggetto <xref:System.Reflection.Assembly> per un assembly.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 L'esempio seguente descrive come ottenere oggetti **Type** per un assembly caricato.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 Dopo aver ottenuto un oggetto **Type**, è possibile ottenere informazioni sui membri del tipo in modi diversi. Ad esempio, per ottenere informazioni su tutti i membri del tipo è possibile chiamare il metodo <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> che ottiene una matrice di oggetti <xref:System.Reflection.MemberInfo> ognuno dei quali descrive un membro del tipo corrente.  
  
 È anche possibile usare i metodi nella classe **Type** per recuperare informazioni su uno o più costruttori, metodi, eventi, campi o proprietà di cui si specifica il nome. Ad esempio, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> incapsula uno costruttore specifico della classe corrente.  
  
 Se è presente un oggetto **Type** è possibile usare la proprietà <xref:System.Type.Module%2A?displayProperty=nameWithType> per ottenere un oggetto che incapsula il modulo contenente il tipo. Usare la proprietà <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> per individuare un oggetto che incapsula l'assembly contenente il modulo. Per ottenere direttamente l'assembly che incapsula il tipo, usare la proprietà <xref:System.Type.Assembly%2A?displayProperty=nameWithType>.  
  
## <a name="systemtype-and-constructorinfo"></a>System.Type e ConstructorInfo  
 L'esempio seguente illustra come elencare i costruttori di una classe, nel caso specifico la classe <xref:System.String>.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a>MemberInfo, MethodInfo, FieldInfo e PropertyInfo  
 Per ottenere informazioni su metodi, proprietà, eventi e campi del tipo, usare gli oggetti <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> o <xref:System.Reflection.PropertyInfo>.  
  
 L'esempio seguente usa **MemberInfo** per elencare il numero di membri della classe **System.IO.File** e usa la proprietà <xref:System.Type.IsPublic%2A> per determinare la visibilità della classe.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 L'esempio seguente analizza il tipo del membro specificato. Viene eseguita una reflection su un membro della classe **MemberInfo** e ne viene elencato il tipo.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 Nell'esempio seguente vengono utilizzate tutte le classi di ** \*informazioni** di <xref:System.Reflection.BindingFlags> Reflection insieme a per elencare tutti i membri (costruttori, campi, proprietà, eventi e metodi) della classe specificata, dividendo i membri in categorie statiche e di istanza.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.BindingFlags>
- <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>
- <xref:System.Type.GetFields%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Reflection.MemberInfo>
- <xref:System.Reflection.ConstructorInfo>
- <xref:System.Reflection.MethodInfo>
- <xref:System.Reflection.FieldInfo>
- <xref:System.Reflection.EventInfo>
- <xref:System.Reflection.ParameterInfo>
- [Reflection e tipi generici](reflection-and-generic-types.md)
