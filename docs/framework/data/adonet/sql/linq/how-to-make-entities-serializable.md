---
title: 'Procedura: Rendere serializzabili le entità'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: fd687ba5dce16baee063f1d3bb9521c6664988b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743284"
---
# <a name="how-to-make-entities-serializable"></a>Procedura: Rendere serializzabili le entità
Quando si genera il codice, è possibile rendere serializzabili le entità. Le classi di entità vengono decorate con l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> e le colonne con l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Gli sviluppatori che usano Visual Studio è possono usare Progettazione relazionale oggetti per questo scopo.  
  
 Se si usa lo strumento da riga di comando SQLMetal, usare il **/serialization** con il `unidirectional` argomento. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 Le righe di comando SQLMetal seguenti consentono di produrre file con entità serializzabili.  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>Vedere anche

- [Serializzazione](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
