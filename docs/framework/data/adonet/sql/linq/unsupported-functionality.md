---
title: Funzionalità non supportata
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: c4ed52a43fe9cf04c8015aad9247e9f2eb2481e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364490"
---
# <a name="unsupported-functionality"></a>Funzionalità non supportata
In LINQ to SQL non è possibile esporre la funzionalità SQL seguente tramite la conversione di costrutti CLR (Common Language Runtime) e .NET Framework esistenti:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Sebbene `LIKE` non sia supportato tramite conversione diretta, una funzionalità analoga esiste nella classe <xref:System.Data.Linq.SqlClient.SqlMethods>. Per altre informazioni, vedere <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     LINQ to SQL dispone di un supporto limitato per `DATEDIFF`. Una funzionalità analoga è presente nella classe <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
-   `ROUND`  
  
     LINQ to SQL dispone di un supporto limitato per `ROUND`. Per ulteriori informazioni, vedere [metodi System. Math](system-math-methods.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati e funzioni](data-types-and-functions.md)
