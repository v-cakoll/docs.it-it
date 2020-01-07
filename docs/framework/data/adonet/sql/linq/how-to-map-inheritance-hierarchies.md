---
title: 'Procedura: eseguire il mapping di gerarchie di ereditarietà'
ms.date: 03/30/2017
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
ms.openlocfilehash: 737cb8743d8fd9c93cd46ebf50fba3fe554a35f2
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634664"
---
# <a name="how-to-map-inheritance-hierarchies"></a>Procedura: eseguire il mapping di gerarchie di ereditarietà
Per implementare il mapping di ereditarietà in LINQ, è necessario specificare gli attributi e le proprietà dell'attributo sulla classe radice della gerarchia di ereditarietà, come descritto nei passaggi seguenti. Gli sviluppatori che usano Visual Studio possono usare i Object Relational Designer per eseguire il mapping delle gerarchie di ereditarietà. Vedere [procedura: configurare l'ereditarietà tramite O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
> [!NOTE]
> Non sono richiesti attributi o proprietà speciali sulle sottoclassi. Notare, in particolare, che le sottoclassi non dispongono dell'attributo <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>Per eseguire il mapping di una gerarchia di ereditarietà  
  
1. Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla classe radice.  
  
2. Aggiungere inoltre alla classe radice un attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> per ogni classe nella struttura gerarchica.  
  
3. Per ogni attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> definire una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
     Questa proprietà contiene un valore che viene visualizzato nella colonna <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> della tabella di database per indicare la classe o sottoclasse a cui appartiene questa riga di dati.  
  
4. Per ogni attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> aggiungere inoltre una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.  
  
     Questa proprietà contiene un valore che specifica a quale classe o sottoclasse corrisponde il valore della chiave.  
  
5. Aggiungere una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> solo a uno degli attributi <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.  
  
     Questa proprietà serve a designare un mapping di *fallback* quando il valore del discriminatore della tabella di database non corrisponde ad alcun valore <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> nei mapping di ereditarietà.  
  
6. Aggiungere una proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> per un attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
     Questa proprietà indica che la colonna specificata contiene il valore <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
## <a name="example"></a>Esempio  
  
> [!NOTE]
> Se si utilizza Visual Studio, è possibile utilizzare il Object Relational Designer per configurare l'ereditarietà. Vedere [procedura: configurare l'ereditarietà tramite O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 Nell'esempio di codice seguente, `Vehicle` viene definito come classe radice e i passaggi precedenti sono stati implementati per descrivere la gerarchia per LINQ.  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Supporto dell'ereditarietà](inheritance-support.md)
- [Procedura: personalizzare classi di entità mediante l'Editor del codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
