---
title: 'Procedura: Specificare nomi di database'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 0daf754edf624410e0ea725acd6c266ccb7828dc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781571"
---
# <a name="how-to-specify-database-names"></a>Procedura: Specificare nomi di database
Usare la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> su un attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> per specificare il nome di un database quando non viene fornito dalla connessione.  
  
 Per alcuni esempi di codice, vedere <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.  
  
### <a name="to-specify-the-name-of-the-database"></a>Per specificare il nome del database  
  
1. Aggiungere l'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute> alla dichiarazione di classe per il database.  
  
2. Aggiungere la proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> all'attributo <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
3. Impostare il valore della proprietà <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> sul nome che si desidera specificare.  
  
## <a name="see-also"></a>Vedere anche

- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
