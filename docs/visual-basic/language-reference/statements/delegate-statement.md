---
title: Istruzione Delegate
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 8dec28620b0409f05007b2c0b1c1fd4494c2d7c8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404758"
---
# <a name="delegate-statement"></a>Istruzione Delegate
Utilizzato per dichiarare un delegato. Un delegato è un tipo di riferimento che fa riferimento a un `Shared` metodo di un tipo o a un metodo di istanza di un oggetto. Per creare un'istanza di questa classe delegata è possibile utilizzare qualsiasi routine con tipi restituiti e parametri corrispondenti. La stored procedure può quindi essere richiamata in un secondo momento tramite l'istanza del delegato.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attrlist`|Facoltativa. Elenco degli attributi che si applicano a questo delegato. Gli attributi sono separati da una virgola. È necessario racchiudere l' [elenco degli attributi](attribute-list.md) tra parentesi angolari (" `<` " e " `>` ").|  
|`accessmodifier`|Facoltativa. Specifica il codice che può accedere al delegato. Può essere uno dei seguenti:<br /><br /> - [Public](../modifiers/public.md). Qualsiasi codice in grado di accedere all'elemento che dichiara il delegato può accedervi.<br />-   [Protetto](../modifiers/protected.md). Solo il codice all'interno della classe del delegato o di una classe derivata può accedervi.<br />-   [Amico](../modifiers/friend.md). Solo il codice all'interno dello stesso assembly può accedere al delegato.<br />- [Privato](../modifiers/private.md). Solo il codice all'interno dell'elemento che dichiara il delegato può accedervi.<br /><br /> - [Amico protetto](../modifiers/protected-friend.md) Solo il codice all'interno della classe del delegato, una classe derivata o lo stesso assembly può accedere al delegato. <br />- [Privato protetto](../modifiers/private-protected.md) Solo il codice all'interno della classe del delegato o in una classe derivata nello stesso assembly può accedere al delegato. |  
|`Shadows`|Facoltativa. Indica che questo delegato dichiara e nasconde un elemento di programmazione con nome identico o un set di elementi di overload in una classe base. È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo.<br /><br /> Un elemento nascosto non è disponibile all'interno della classe derivata che lo nasconde, a meno che l'elemento di shadowing sia inaccessibile. Se, ad esempio, un `Private` elemento nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere all'elemento `Private` accede all'elemento della classe di base.|  
|`Sub`|Facoltativo, ma `Sub` `Function` deve essere visualizzato o. Dichiara questa procedura come una procedura di delega `Sub` che non restituisce un valore.|  
|`Function`|Facoltativo, ma `Sub` `Function` deve essere visualizzato o. Dichiara questa routine come una routine di delegato `Function` che restituisce un valore.|  
|`name`|Obbligatorio. Nome del tipo delegato. segue le convenzioni di denominazione delle variabili standard.|  
|`typeparamlist`|Facoltativa. Elenco di parametri di tipo per questo delegato. Più parametri di tipo sono separati da virgole. Facoltativamente, ogni parametro di tipo può essere dichiarato Variant usando `In` i `Out` modificatori generici e. È necessario racchiudere l' [elenco dei tipi](type-list.md) tra parentesi e introducerlo con la `Of` parola chiave.|  
|`parameterlist`|Facoltativa. Elenco di parametri passati alla procedura quando viene chiamato. È necessario racchiudere l' [elenco di parametri](parameter-list.md) tra parentesi.|  
|`type`|Obbligatorio se si specifica una `Function` stored procedure. Tipo di dati del valore restituito.|  
  
## <a name="remarks"></a>Commenti  
 L' `Delegate` istruzione definisce il parametro e i tipi restituiti di una classe delegata. Per creare un'istanza di questa classe delegata è possibile utilizzare qualsiasi routine con i tipi restituiti e i parametri corrispondenti. La stored procedure può quindi essere richiamata per mezzo dell'istanza del delegato, chiamando il metodo del delegato `Invoke` .  
  
 I delegati possono essere dichiarati a livello di spazio dei nomi, modulo, classe o struttura, ma non all'interno di una routine.  
  
 Ogni classe delegata definisce un costruttore a cui viene passata la specifica di un metodo dell'oggetto. Un argomento di un costruttore di delegati deve essere un riferimento a un metodo o a un'espressione lambda.  
  
 Per specificare un riferimento a un metodo, usare la sintassi seguente:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Il tipo in fase di compilazione dell'elemento `expression` deve essere il nome di una classe o un'interfaccia contenente un metodo con il nome specificato la cui firma corrisponde a quella della classe delegata. Il metodo `methodname` può essere o un metodo condiviso o un metodo di istanza. `methodname` non è un elemento facoltativo, anche se si crea un delegato per il metodo predefinito della classe.  
  
 Per specificare un'espressione lambda, usare la sintassi seguente:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 La firma della funzione deve corrispondere a quella del tipo delegato. Per ulteriori informazioni sulle espressioni lambda, vedere [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Per altre informazioni sui delegati, vedere [Delegati](../../programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzata l' `Delegate` istruzione per dichiarare un delegato per l'utilizzo di due numeri e la restituzione di un numero. Il `DelegateTest` metodo accetta un'istanza di un delegato di questo tipo e la usa per operare su coppie di numeri.  
  
 [!code-vb[VbVbalrDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore AddressOf](../operators/addressof-operator.md)
- [Di](of-clause.md)
- [Delegati](../../programming-guide/language-features/delegates/index.md)
- [Procedura: Usare una classe generica](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../modifiers/in-generic-modifier.md)
- [Out](../modifiers/out-generic-modifier.md)
