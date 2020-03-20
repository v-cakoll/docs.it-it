---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: 06c4200434f443446e8981dcefe2baf43b1af4b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149895"
---
# <a name="treat-entity-sql"></a>TREAT (Entity SQL)
Consente di trattare un oggetto di un tipo di base particolare come oggetto del tipo derivato specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a>Argomenti  
 `expression`  
 Qualsiasi espressione di query valida che restituisce un'entità.  
  
> [!NOTE]
> Il tipo dell'espressione specificata deve essere un sottotipo del tipo di dati specificato oppure il tipo di dati deve essere un sottotipo del tipo di espressione.  
  
 `type`  
 Tipo di entità. Il tipo deve essere qualificato da uno spazio dei nomi.  
  
> [!NOTE]
> L'espressione specificata deve essere un sottotipo del tipo di dati specificato oppure il tipo di dati deve essere un sottotipo dell'espressione.  
  
## <a name="return-value"></a>Valore restituito  
 Valore del tipo di dati specificato.  
  
## <a name="remarks"></a>Osservazioni  
 TREAT viene usato per eseguire l'upcast tra classi correlate. Se, ad esempio, `Employee` deriva da `Person` e p è di tipo `Person`, `TREAT(p AS NamespaceName.Employee)` consente di eseguire l'upcast di un'istanza generica di `Person` a `Employee`, ovvero consente di trattare p come `Employee`.  
  
 TREAT viene usato negli scenari di ereditarietà dove è possibile eseguire una query simile alla seguente:  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)
```  
  
 Questa query consente di eseguire l'upcast delle entità `Person` al tipo `Employee` . Se il valore di p non è di tipo `Employee`, l'espressione restituisce il valore `null`.  
  
> [!NOTE]
> L'espressione `Employee` specificata deve essere un sottotipo del tipo `Person`di dati specificato oppure il tipo di dati deve essere un sottotipo dell'espressione. In caso contrario, l'espressione comporterà la generazione di un errore in fase di compilazione.  
  
 Nella tabella seguente viene illustrato il comportamento di TREAT su alcuni modelli tipici e su alcuni modelli meno comuni. Tutte le eccezioni vengono generate sul lato client prima che il provider venga richiamato:  
  
|Modello|Comportamento|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|Restituisce `DbNull`.|  
|`TREAT (null AS ComplexType)`|Genera un'eccezione.|  
|`TREAT (null AS RowType)`|Genera un'eccezione/|  
|`TREAT (EntityType AS EntityType)`|Restituisce `EntityType` o `null`.|  
|`TREAT (ComplexType AS ComplexType)`|Genera un'eccezione.|  
|`TREAT (RowType AS RowType)`|Genera un'eccezione.|  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore TREAT per convertire un oggetto del tipo Course in una raccolta di oggetti del tipo OnsiteCourse. La query è basata sul [modello School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-sql[DP EntityServices Concepts#TREAT_ISOF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#treat_isof)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Tipi strutturati nullable](nullable-structured-types-entity-sql.md)
