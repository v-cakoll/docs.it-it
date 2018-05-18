---
title: 'Procedura: Eseguire modifiche di base delle stringhe in .NET Framework'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e8c6c3f9b7ec418fdbf6365a3e7d90fe65e9caa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Procedura: Eseguire modifiche di base delle stringhe in .NET
Nell'esempio seguente vengono usati alcuni dei metodi descritti nell'argomento [Operazioni di base su stringhe](../../../docs/standard/base-types/basic-string-operations.md) per costruire una classe con la quale modificare le stringhe, come può avvenire in un'applicazione reale. Nella classe `MailToData` vengono archiviati il nome e l'indirizzo di un utente in proprietà separate e viene usato un modo per combinare i campi `City`, `State` e `Zip` in una singola stringa da visualizzare all'utente. Questa classe consente anche all'utente di immettere la città, lo stato e il codice postale ZIP (Stati Uniti) sotto forma di singola stringa. L'applicazione automaticamente analizza la singola stringa e immette le informazioni corrette nella proprietà corrispondente.  
  
 Per semplicità, in questo esempio viene usata un'applicazione console con un'interfaccia della riga di comando.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 Dopo aver eseguito il codice precedente, all'utente viene chiesto di immettere nome e indirizzo. L'applicazione inserisce le informazioni nelle proprietà corrette e visualizza le informazioni all'utente, creando una singola stringa che contiene la città, lo stato e il codice postale ZIP (Stati Uniti).  
  
## <a name="see-also"></a>Vedere anche  
 [Operazioni di base su stringhe](../../../docs/standard/base-types/basic-string-operations.md)
