---
title: Funzioni stringa canoniche
ms.date: 03/30/2017
ms.assetid: 5e2cbebd-5df3-47c7-b0e2-49a17ab22bfb
ms.openlocfilehash: d4758f8325b99bc4bd91575dd774d2dabde1f925
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027988"
---
# <a name="string-canonical-functions"></a>Funzioni stringa canoniche
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] include funzioni canoniche string.  
  
## <a name="remarks"></a>Note  
 Nella tabella seguente sono illustrate le funzioni canoniche di stringa [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|`Concat(string1, string2)`|Restituisce una stringa che contiene l'oggetto `string2` aggiunto a `string1`.<br /><br /> **Argomenti**<br /><br /> `string1`: la stringa alla quale è aggiunto `string2`.<br /><br /> `string2`: la stringa aggiunta a `string1`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`. Se la lunghezza della stringa del valore restituito è superiore alla lunghezza massima consentita, si verificherà un errore.<br /><br /> **Esempio**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Contains(string, target)`|Restituisce `true` se `target` è contenuto in `string`.<br /><br /> **Argomenti**<br /><br /> `string`: la stringa nella quale viene eseguita la ricerca.<br /><br /> `target`: la stringa di destinazione che viene cercata.<br /><br /> **Valore restituito**<br /><br /> `true` se `target` è contenuto in `string`; in caso contrario, `false`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns true.`<br /><br /> `Contains('abc', 'bc')`|  
|`EndsWith(string, target)`|Restituisce `true` se `target` termina con `string`.<br /><br /> **Argomenti**<br /><br /> `string`: la stringa nella quale viene eseguita la ricerca.<br /><br /> `target`: la stringa di destinazione che viene cercata alla fine di `string`.<br /><br /> **Valore restituito**<br /><br /> `True` se `string` termina con `target`; in caso contrario, `false`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns true.`<br /><br /> `EndsWith('abc', 'bc')` **Nota:** se si utilizza il provider di dati di SQL Server, questa funzione restituisce `false` se la stringa viene archiviata in una colonna stringa di lunghezza fissa e `target` è una costante. In questo caso, la ricerca viene eseguita nell'intera stringa, inclusa la spaziatura interna finale. Una possibile soluzione alternativa consiste nel tagliare la stringa a lunghezza, come nell'esempio seguente: `EndsWith(TRIM(string), target)`|  
|`IndexOf(target, string)`|Restituisce la posizione di `target` in `string` o 0 se non viene trovato. Restituisce 1 per indicare l'inizio di `string`. La numerazione dell'indice inizia da 1.<br /><br /> **Argomenti**<br /><br /> `target`: la stringa che viene cercata.<br /><br /> `string`: la stringa nella quale viene eseguita la ricerca.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Int32`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns 4.`<br /><br /> `IndexOf('xyz', 'abcxyz')`|  
|`Left(string, length)`|Restituisce i primi caratteri `length` dal lato sinistro di `string`. Se la lunghezza di `string` è inferiore a `length`, viene restituita la stringa intera.<br /><br /> **Argomenti**<br /><br /> `string`: valore `String`.<br /><br /> `length`: `Int16`,`Int32`, `Int64` o `Byte`. `length` non può essere minore di zero.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns abc.`<br /><br /> `Left('abcxyz', 3)`|  
|`Length(string)`|Restituisce la lunghezza (`Int32`), espressa in caratteri, della stringa.<br /><br /> **Argomenti**<br /><br /> `string`: valore `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `Int32`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns 6.`<br /><br /> `Legth('abcxyz')`|  
|`LTrim(string)`|Restituisce `string` senza gli spazi vuoti iniziali.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns abc.`<br /><br /> `LTrim('   abc')`|  
|`Replace(string1, string2, string3)`|Restituisce `string1`, con tutte le occorrenze di `string2` sostituite da `string3`.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Reverse(string)`|Restituisce `string` con l'ordine dei caratteri invertito.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns dcba.`<br /><br /> `Reverse('abcd')`|  
|`Right(string, length)`|Restituisce l'ultimo `length` caratteri dal `string`. Se la lunghezza di `string` è inferiore a `length`, viene restituita la stringa intera.<br /><br /> **Argomenti**<br /><br /> `string`: valore `String`.<br /><br /> `length`: `Int16`,`Int32`, `Int64` o `Byte`. `length` non può essere minore di zero.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Right('abcxyz', 3)`|  
|`RTrim(string)`|Restituisce `string` senza spazi vuoti finali.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.|  
|`Substring(string, start, length)`|Restituisce la sottostringa della stringa che inizia nella posizione `start`, con una lunghezza di `length` caratteri. Il valore iniziale 1 indica il primo carattere della stringa. La numerazione dell'indice inizia da 1.<br /><br /> **Argomenti**<br /><br /> `string`: valore `String`.<br /><br /> `start`: tipo `Int16`, `Int32`, `Int64` e `Byte`. `start` non può essere minore di uno.<br /><br /> `length`: tipo `Int16`, `Int32`, `Int64` e `Byte`. `length` non può essere minore di zero.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Substring('abcxyz', 4, 3)`|  
|`StartsWith(string, target)`|Restituisce `true` se `string` inizia con `target`.<br /><br /> **Argomenti**<br /><br /> `string`: la stringa nella quale viene eseguita la ricerca.<br /><br /> `target`: la stringa di destinazione che viene cercata all'inizio di `string`.<br /><br /> **Valore restituito**<br /><br /> `True` se `string` inizia con `target`; in caso contrario, `false`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns true.`<br /><br /> `StartsWith('abc', 'ab')`|  
|`ToLower(string)`|Restituisce `string` con tutti i caratteri maiuscoli convertiti in caratteri minuscoli.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns abc.`<br /><br /> `ToLower('ABC')`|  
|`ToUpper(string)`|Restituisce `string` con i caratteri minuscoli convertiti in caratteri maiuscoli.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns ABC.`<br /><br /> `ToUpper('abc')`|  
|`Trim(string)`|Restituisce `string` senza spazi vuoti iniziali e finali.<br /><br /> **Argomenti**<br /><br /> Oggetto `String`.<br /><br /> **Valore restituito**<br /><br /> Oggetto `String`.<br /><br /> **Esempio**<br /><br /> `-- The following example returns abc.`<br /><br /> `Trim('      abc   ')`|  
  
 Queste funzioni restituiscono `null` se l'input è `null`.  
  
 Una funzionalità equivalente è disponibile nel provider gestito del client Microsoft SQL. Per altre informazioni, vedere [SqlClient per funzioni Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni canoniche](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
