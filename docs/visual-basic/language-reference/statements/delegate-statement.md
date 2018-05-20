---
title: Istruzione Delegate
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 3965dc2d71ec9356cdb38d5ddcd4e00f9259951a
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2018
---
# <a name="delegate-statement"></a>Istruzione Delegate
Usato per dichiarare un delegato. Un delegato è un tipo di riferimento che fa riferimento a un `Shared` metodo di un tipo o a un metodo di istanza di un oggetto. Qualsiasi routine con parametri e tipi restituiti corrispondenti può essere utilizzato per creare un'istanza della classe delegata. La procedura può quindi in un secondo momento richiamata mediante l'istanza del delegato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attrlist`|Facoltativo. Elenco di attributi che si applicano a questo delegato. Gli attributi sono separati da una virgola. È necessario racchiudere il [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md) tra parentesi quadre ("`<`"e"`>`").|  
|`accessmodifier`|Facoltativo. Specifica il tipo di codice può accedere al delegato. Può essere uno dei seguenti:<br /><br /> - [Pubblica](../../../visual-basic/language-reference/modifiers/public.md). Può accedere qualsiasi codice che è possibile accedere all'elemento che dichiara il delegato.<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md). Solo il codice incluso nella classe del delegato o di una classe derivata può accedervi.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Solo il codice all'interno dello stesso assembly può accedere al delegato.<br />- [Privato](../../../visual-basic/language-reference/modifiers/private.md). Può accedere solo codice all'interno dell'elemento che dichiara il delegato.<br /><br /> - [Protected Friend](../../language-reference/modifiers/protected-friend.md) solo codice all'interno dello stesso assembly, classe del delegato o una classe derivata può accedere al delegato. <br />- [Protetto privato](../../language-reference/modifiers/private-protected.md) solo codice all'interno di classe del delegato o in una classe derivata nello stesso assembly può accedere al delegato. |  
|`Shadows`|Facoltativo. Indica che il delegato ridichiara e nasconde un elemento di programmazione omonimo o un set di elementi in overload di una classe di base. È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo.<br /><br /> Un elemento nascosto non è disponibile all'interno della classe derivata che lo nasconde, a meno che l'elemento di shadowing sia inaccessibile. Ad esempio, se un `Private` elemento nasconde un elemento della classe base, il codice che non dispone dell'autorizzazione per accedere il `Private` elemento accede invece all'elemento della classe base.|  
|`Sub`|Parametro facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Questa procedura come un delegato dichiara `Sub` routine che restituisce un valore.|  
|`Function`|Parametro facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Questa procedura come un delegato dichiara `Function` procedure che restituisce un valore.|  
|`name`|Obbligatorio. Nome del tipo delegato. segue le convenzioni di denominazione standard variabile.|  
|`typeparamlist`|Facoltativo. Elenco di parametri di tipo per questo delegato. Più parametri di tipo sono separati da virgole. Facoltativamente, ogni parametro di tipo può essere dichiarato variante mediante `In` e `Out` modificatori generici. È necessario racchiudere il [tipo elenco](../../../visual-basic/language-reference/statements/type-list.md) tra parentesi e introdotto con la `Of` (parola chiave).|  
|`parameterlist`|Facoltativo. Elenco di parametri che vengono passati alla procedura quando viene chiamato. È necessario racchiudere il [elenco parametri](../../../visual-basic/language-reference/statements/parameter-list.md) tra parentesi.|  
|`type`|Necessario se si specifica un `Function` stored procedure. Tipo di dati del valore restituito.|  
  
## <a name="remarks"></a>Note  
 Il `Delegate` istruzione definisce i parametri e tipi restituiti di una classe delegata. Qualsiasi routine con parametri e tipi restituiti corrispondenti può essere utilizzato per creare un'istanza della classe delegata. La procedura può successivamente essere utilizzata in tramite l'istanza del delegato, chiamando il delegato `Invoke` metodo.  
  
 I delegati possono essere dichiarati a livello di struttura di spazio dei nomi, modulo, classe o, ma non all'interno di una stored procedure.  
  
 Ogni classe delegata definisce un costruttore a cui viene passata la specifica di un metodo dell'oggetto. Un argomento di un costruttore di delegati deve essere un riferimento a un metodo o a un'espressione lambda.  
  
 Per specificare un riferimento a un metodo, usare la sintassi seguente:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Il tipo in fase di compilazione dell'elemento `expression` deve essere il nome di una classe o un'interfaccia contenente un metodo con il nome specificato la cui firma corrisponde a quella della classe delegata. Il metodo `methodname` può essere o un metodo condiviso o un metodo di istanza. `methodname` non è un elemento facoltativo, anche se si crea un delegato per il metodo predefinito della classe.  
  
 Per specificare un'espressione lambda, usare la sintassi seguente:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 La firma della funzione deve corrispondere a quella del tipo delegato. Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda in C++](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Per ulteriori informazioni sui delegati, vedere [delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Delegate` istruzione per dichiarare un delegato per operazioni su due numeri e la restituzione di un numero. Il `DelegateTest` metodo accetta un'istanza di questo tipo di delegato e lo usa per operare su coppie di numeri.  
  
 [!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Covarianza e controvarianza](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
