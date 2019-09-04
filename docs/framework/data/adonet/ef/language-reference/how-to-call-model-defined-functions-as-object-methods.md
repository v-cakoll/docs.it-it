---
title: 'Procedura: Chiamare funzioni definite dal modello come metodi di oggetto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 787ead2c52f874af2ca1a02bf009da40cee875ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250763"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a>Procedura: Chiamare funzioni definite dal modello come metodi di oggetto
In questo argomento viene descritto come chiamare una funzione definita dal modello come metodo in un oggetto <xref:System.Data.Objects.ObjectContext> oppure come metodo statico di una classe personalizzata. Una *funzione definita dal modello* è una funzione definita nel modello concettuale. Le procedure descritte in questo argomento mostrano come chiamare queste funzioni direttamente anziché chiamarle da query LINQ to Entities. Per informazioni sulla chiamata di funzioni definite dal modello in LINQ to Entities query, [vedere How to: Chiamare funzioni definite dal modello nelle query](how-to-call-model-defined-functions-in-queries.md).  
  
 Sia che si chiami una funzione definita dal modello come metodo <xref:System.Data.Objects.ObjectContext> o come metodo statico in una classe personalizzata, è necessario innanzitutto eseguire il mapping del metodo alla funzione definita dal modello con un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>. Tuttavia, quando si definisce un metodo nella classe <xref:System.Data.Objects.ObjectContext>, è necessario usare la proprietà <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> per esporre il provider LINQ, mentre quando si definisce un metodo statico in una classe personalizzata, è necessario usare la proprietà <xref:System.Linq.IQueryable.Provider%2A> per esporre il provider LINQ. Per altre informazioni, vedere gli esempi che seguono le procedure.  
  
 Le procedure descritte di seguito forniscono strutture di alto livello per la chiamata di una funzione definita dal modello come metodo in un oggetto <xref:System.Data.Objects.ObjectContext> e come metodo statico in una classe personalizzata. Negli esempi che seguono vengono forniti dettagli aggiuntivi sui passaggi delle procedure. In queste procedure si presuppone che sia stata definita una funzione nel modello concettuale. Per altre informazioni, vedere [Procedura: Definire funzioni personalizzate nel modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))concettuale.  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a>Per chiamare una funzione definita dal modello come metodo in un oggetto ObjectContext  
  
1. Aggiungere un file di origine per estendere la classe parziale derivata dalla classe <xref:System.Data.Objects.ObjectContext>, generata automaticamente dagli strumenti di Entity Framework. La definizione dello stub CLR in un file di origine separato impedirà la perdita delle modifiche durante la rigenerazione del file.  
  
2. Aggiungere un metodo Common Language Runtime (CLR) alla classe <xref:System.Data.Objects.ObjectContext> che:  
  
    - Esegue il mapping alla funzione definita nel modello concettuale. Per eseguire il mapping del metodo, è necessario applicare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo. Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale. La risoluzione del nome della funzione per LINQ rileva la distinzione tra maiuscole e minuscole.  
  
    - Restituisce i risultati del metodo <xref:System.Linq.IQueryProvider.Execute%2A> che viene restituito dalla proprietà <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>.  
  
3. Chiamare il metodo come membro di un'istanza della classe <xref:System.Data.Objects.ObjectContext>.  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a>Per chiamare una funzione definita dal modello come metodo statico in una classe personalizzata  
  
1. Aggiungere una classe all'applicazione con un metodo statico che:  
  
    - Esegue il mapping alla funzione definita nel modello concettuale. Per eseguire il mapping del metodo, è necessario applicare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo. Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale.  
  
    - Accetta un argomento <xref:System.Linq.IQueryable>.  
  
    - Restituisce i risultati del metodo <xref:System.Linq.IQueryProvider.Execute%2A> che viene restituito dalla proprietà <xref:System.Linq.IQueryable.Provider%2A>.  
  
2. Chiamare il metodo come membro di un metodo statico nella classe personalizzata  
  
## <a name="example"></a>Esempio  
 **Chiamata di una funzione definita dal modello come metodo in un oggetto ObjectContext**  
  
 Nell'esempio seguente viene mostrato come chiamare una funzione definita dal modello come metodo in un oggetto <xref:System.Data.Objects.ObjectContext>. Nell'esempio viene utilizzato il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).  
  
 Considerare la seguente funzione del modello concettuale che restituisce il ricavo di prodotto per un prodotto specificato. Per informazioni sull'aggiunta della funzione al modello concettuale, vedere [procedura: Definire funzioni personalizzate nel modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))concettuale.  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a>Esempio  
 Nel codice seguente viene aggiunto un metodo alla classe `AdventureWorksEntities` che esegue il mapping alla suddetta funzione del modello concettuale.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene chiamato il metodo sopraindicato per visualizzare il ricavo di prodotto per un prodotto specificato:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene mostrato come chiamare una funzione definita dal modello che restituisce una raccolta (come un oggetto <xref:System.Linq.IQueryable%601>). Considerare la seguente funzione del modello concettuale che restituisce tutti i `SalesOrderDetails` per un dato ID di prodotto.  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene aggiunto un metodo alla classe `AdventureWorksEntities` che esegue il mapping alla suddetta funzione del modello concettuale.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene chiamato il metodo. Si noti che la query <xref:System.Linq.IQueryable%601> restituita è ridefinita ulteriormente in modo da restituire i totali delle righe per ogni `SalesOrderDetail`.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a>Esempio  
 **Chiamata di una funzione definita dal modello come metodo statico in una classe personalizzata**  
  
 Nell'esempio seguente viene dimostrato come chiamare una funzione definita dal modello come metodo statico in una classe personalizzata. Nell'esempio viene utilizzato il [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).  
  
> [!NOTE]
> Quando si chiama una funzione definita dal modello come metodo statico in una classe personalizzata, la funzione definita dal modello deve accettare una raccolta e restituire un'aggregazione di valori nella raccolta.  
  
 Considerare la seguente funzione del modello concettuale che restituisce il ricavo di prodotto per una raccolta SalesOrderDetail. Per informazioni sull'aggiunta della funzione al modello concettuale, vedere [procedura: Definire funzioni personalizzate nel modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))concettuale.  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene aggiunta una classe all'applicazione contenente un metodo statico che esegue il mapping alla suddetta funzione del modello concettuale.  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene chiamato il metodo sopraindicato per visualizzare il ricavo di prodotto per una raccolta SalesOrderDetail:  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
- [Chiamata di funzioni in query di LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
