---
title: . (Accesso ai membri) (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c90c908e567ac05f344292411978ff0c80919a65
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="-member-access-entity-sql"></a>. (Accesso ai membri) (Entity SQL)
L'operatore punto (.) è il [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatore di accesso al membro. L'operatore di accesso ai membri viene usato per produrre il valore di una proprietà o di un campo di un'istanza del tipo di modello concettuale strutturale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Istanza di un tipo di modello concettuale strutturale.  
  
 `identifier`  
 Proprietà o campo che appartiene a un'istanza dell'oggetto.  
  
## <a name="remarks"></a>Note  
 L'operatore punto (.) può essere usato per estrarre campi da un record, analogamente all'estrazione di proprietà di un tipo di entità o complesso. Se, ad esempio, un oggetto n di tipo Name è un membro del tipo Person e p è un'istanza del tipo Person, p.n è un'espressione di accesso ai membri valida che restituisce un valore di tipo Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
