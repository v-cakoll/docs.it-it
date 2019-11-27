---
title: Istruzione Delegate
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 662d2c3c0767adfe406e0a6f1b1e6dccd704e795
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354080"
---
# <a name="delegate-statement"></a>Istruzione Delegate
Utilizzato per dichiarare un delegato. Un delegato è un tipo di riferimento che fa riferimento a un metodo di `Shared` di un tipo o a un metodo di istanza di un oggetto. Per creare un'istanza di questa classe delegata è possibile utilizzare qualsiasi routine con tipi restituiti e parametri corrispondenti. La stored procedure può quindi essere richiamata in un secondo momento tramite l'istanza del delegato.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attrlist`|Facoltativa. Elenco degli attributi che si applicano a questo delegato. Gli attributi sono separati da una virgola. È necessario racchiudere l' [elenco degli attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi angolari ("`<`" e "`>`").|  
|`accessmodifier`|Facoltativa. Specifica il codice che può accedere al delegato. Può essere uno dei collegamenti seguenti:<br /><br /> - [public](../../../visual-basic/language-reference/modifiers/public.md). Qualsiasi codice in grado di accedere all'elemento che dichiara il delegato può accedervi.<br />-   [protetto](../../../visual-basic/language-reference/modifiers/protected.md). Solo il codice all'interno della classe del delegato o di una classe derivata può accedervi.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Solo il codice all'interno dello stesso assembly può accedere al delegato.<br />- [privato](../../../visual-basic/language-reference/modifiers/private.md). Solo il codice all'interno dell'elemento che dichiara il delegato può accedervi.<br /><br /> - solo codice [Friend protetto](../../language-reference/modifiers/protected-friend.md) nella classe del delegato, una classe derivata o lo stesso assembly può accedere al delegato. <br />- codice [privato protetto](../../language-reference/modifiers/private-protected.md) solo all'interno della classe del delegato o in una classe derivata nello stesso assembly può accedere al delegato. |  
|`Shadows`|Facoltativa. Indica che questo delegato dichiara e nasconde un elemento di programmazione con nome identico o un set di elementi di overload in una classe base. È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo.<br /><br /> Un elemento nascosto non è disponibile all'interno della classe derivata che lo nasconde, a meno che l'elemento di shadowing sia inaccessibile. Se, ad esempio, un elemento `Private` nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere all'elemento `Private` accede invece all'elemento della classe di base.|  
|`Sub`|Facoltativo, ma è necessario che sia presente `Sub` o `Function`. Dichiara questa procedura come delegato `Sub` routine che non restituisce un valore.|  
|`Function`|Facoltativo, ma è necessario che sia presente `Sub` o `Function`. Dichiara questa routine come delegato `Function` routine che restituisce un valore.|  
|`name`|Obbligatoria. Nome del tipo delegato. segue le convenzioni di denominazione delle variabili standard.|  
|`typeparamlist`|Facoltativa. Elenco di parametri di tipo per questo delegato. Più parametri di tipo sono separati da virgole. Facoltativamente, ogni parametro di tipo può essere dichiarato Variant usando `In` e `Out` modificatori generici. È necessario racchiudere l' [elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md) tra parentesi e introducerlo con la parola chiave `Of`.|  
|`parameterlist`|Facoltativa. Elenco di parametri passati alla procedura quando viene chiamato. È necessario racchiudere l' [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md) tra parentesi.|  
|`type`|Obbligatorio se si specifica una procedura `Function`. Tipo di dati del valore restituito.|  
  
## <a name="remarks"></a>Osservazioni  
 L'istruzione `Delegate` definisce il parametro e i tipi restituiti di una classe delegata. Per creare un'istanza di questa classe delegata è possibile utilizzare qualsiasi routine con i tipi restituiti e i parametri corrispondenti. La stored procedure può quindi essere richiamata per mezzo dell'istanza del delegato, chiamando il metodo `Invoke` del delegato.  
  
 I delegati possono essere dichiarati a livello di spazio dei nomi, modulo, classe o struttura, ma non all'interno di una routine.  
  
 Ogni classe delegata definisce un costruttore a cui viene passata la specifica di un metodo dell'oggetto. Un argomento di un costruttore di delegati deve essere un riferimento a un metodo o a un'espressione lambda.  
  
 Per specificare un riferimento a un metodo, usare la sintassi seguente:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Il tipo in fase di compilazione dell'elemento `expression` deve essere il nome di una classe o un'interfaccia contenente un metodo con il nome specificato la cui firma corrisponde a quella della classe delegata. Il metodo `methodname` può essere o un metodo condiviso o un metodo di istanza. `methodname` non è un elemento facoltativo, anche se si crea un delegato per il metodo predefinito della classe.  
  
 Per specificare un'espressione lambda, usare la sintassi seguente:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 La firma della funzione deve corrispondere a quella del tipo delegato. Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda in C++](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Per altre informazioni sui delegati, vedere [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l'istruzione `Delegate` per dichiarare un delegato per l'utilizzo di due numeri e la restituzione di un numero. Il metodo `DelegateTest` accetta un'istanza di un delegato di questo tipo e lo usa per operare su coppie di numeri.  
  
 [!code-vb[VbVbalrDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
