---
title: 'Procedura: Chiamare funzioni definite dal modello in query'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: 33f26896dd0d4ff08beb4a011fa6bd468cba7207
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250752"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a>Procedura: Chiamare funzioni definite dal modello in query
In questo argomento viene descritto come chiamare funzioni definite nel modello concettuale dall'interno di LINQ to Entities query.  
  
 La procedura riportata di seguito fornisce una struttura di alto livello per la chiamata di una funzione definita dal modello dall'interno di una query LINQ to Entities. Nell'esempio che segue vengono forniti dettagli aggiuntivi sui passaggi della procedura. In questa procedura si presuppone che sia stata definita una funzione nel modello concettuale. Per altre informazioni, vedere [Procedura: Definire funzioni personalizzate nel modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))concettuale.  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a>Per chiamare una funzione definita nel modello concettuale  
  
1. Aggiungere un metodo CLR (Common Language Runtime) all'applicazione che esegue il mapping alla funzione definita nel modello concettuale. Per eseguire il mapping del metodo, è necessario applicare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo. Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale. La risoluzione del nome della funzione per LINQ rileva la distinzione tra maiuscole e minuscole.  
  
2. Chiamare la funzione in una query LINQ to Entities.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare una funzione definita nel modello concettuale dall'interno di una query LINQ to Entities. Nell'esempio viene usato il modello School. Per informazioni sul modello School, vedere [creazione del database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) e [generazione del file School. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).  
  
 La funzione del modello concettuale seguente restituisce il numero di anni di servizio di un docente. Per informazioni sull'aggiunta della funzione a un modello concettuale, [vedere Procedura: Definire funzioni personalizzate nel modello](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))concettuale.  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a>Esempio  
 Successivamente aggiungere il metodo seguente all'applicazione e usare un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> per eseguirne il mapping alla funzione del modello concettuale:  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a>Esempio  
 A questo punto è possibile chiamare la funzione del modello concettuale dall'interno di una query LINQ to Entities. Nel codice seguente viene chiamato il metodo per visualizzare tutti i docenti assunti da più di dieci anni:  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Query in LINQ to Entities](queries-in-linq-to-entities.md)
- [Chiamata di funzioni in query di LINQ to Entities](calling-functions-in-linq-to-entities-queries.md)
- [Procedura: Chiamare funzioni definite dal modello come metodi di oggetto](how-to-call-model-defined-functions-as-object-methods.md)
