---
title: Funzionalità non supportata
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: fb030a5f212be71d99b66f101e5e8411fbe4de33
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64618147"
---
# <a name="unsupported-functionality"></a>Funzionalità non supportata
In LINQ to SQL non è possibile esporre la funzionalità SQL seguente tramite la conversione di costrutti CLR (Common Language Runtime) e .NET Framework esistenti:  
  
- `STDDEV`  
  
- `LIKE`  
  
     Sebbene `LIKE` non sia supportato tramite conversione diretta, una funzionalità analoga esiste nella classe <xref:System.Data.Linq.SqlClient.SqlMethods>. Per altre informazioni, vedere <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
- `DATEDIFF`  
  
     LINQ to SQL dispone di un supporto limitato per `DATEDIFF`. Una funzionalità analoga è presente nella classe <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
- `ROUND`  
  
     LINQ to SQL dispone di un supporto limitato per `ROUND`. Per altre informazioni, vedere [metodi System. Math](system-math-methods.md).  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di dati e funzioni](data-types-and-functions.md)
