---
title: "Procedura: eseguire il mapping di gerarchie di ereditarietà"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b27c779b-9355-4dc7-b95f-7dfd504b6e48
dev_langs:
- csharp
- vb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e9d6215335f6a58de194253cbfe1e539f50d6d84
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-map-inheritance-hierarchies"></a>Procedura: eseguire il mapping di gerarchie di ereditarietà
Per implementare il mapping di ereditarietà in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], è necessario specificare gli attributi e le relative proprietà sulla classe radice della gerarchia di ereditarietà, come descritto nei passaggi seguenti. Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per eseguire il mapping delle gerarchie di ereditarietà. Vedere [procedura: configurare l'ereditarietà tramite O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer).  
  
> [!NOTE]
>  Non sono richiesti attributi o proprietà speciali sulle sottoclassi. Notare, in particolare, che le sottoclassi non dispongono dell'attributo <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
### <a name="to-map-an-inheritance-hierarchy"></a>Per eseguire il mapping di una gerarchia di ereditarietà  
  
1.  Aggiungere l'attributo <xref:System.Data.Linq.Mapping.TableAttribute> alla classe radice.  
  
2.  Aggiungere inoltre alla classe radice un attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> per ogni classe nella struttura gerarchica.  
  
3.  Per ogni attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> definire una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
     Questa proprietà contiene un valore che viene visualizzato nella colonna <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> della tabella di database per indicare la classe o sottoclasse a cui appartiene questa riga di dati.  
  
4.  Per ogni attributo <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> aggiungere inoltre una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>.  
  
     Questa proprietà contiene un valore che specifica a quale classe o sottoclasse corrisponde il valore della chiave.  
  
5.  Aggiungere una proprietà <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute> solo a uno degli attributi <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>.  
  
     Questa proprietà viene utilizzata per definire un *fallback* mapping quando il valore discriminante dalla tabella di database non corrisponde a qualsiasi <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A> valore nei mapping di ereditarietà.  
  
6.  Aggiungere una proprietà <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A> per un attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
     Questa proprietà indica che la colonna specificata contiene il valore <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>.  
  
## <a name="example"></a>Esempio  
  
> [!NOTE]
>  Se si usa [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], è possibile adoperare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per configurare l'ereditarietà. Vedere [procedura: configurare l'ereditarietà tramite O/R Designer](/visualstudio/data-tools/how-to-configure-inheritance-by-using-the-o-r-designer)  
  
 Nell'esempio di codice seguente `Vehicle` viene definita come classe radice e i passaggi precedenti sono stati implementati per descrivere la gerarchia per [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 [!code-csharp[DLinqCustomize#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#4)]
 [!code-vb[DLinqCustomize#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 [Supporto dell'ereditarietà](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)  
 [Procedura: personalizzare classi di entità mediante l'Editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
