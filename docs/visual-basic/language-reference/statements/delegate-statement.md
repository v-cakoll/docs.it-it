---
title: Delegare l'istruzione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 4718c0a6e332d644a7f54c79246df95f841058d0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45616851"
---
# <a name="delegate-statement"></a>Istruzione Delegate
Usata per dichiarare un delegato. Un delegato è un tipo di riferimento che fa riferimento a un `Shared` metodo di un tipo o a un metodo di istanza di un oggetto. Qualsiasi routine con parametri e tipi restituiti corrispondenti può utilizzabile per creare un'istanza di questa classe delegata. La procedura può quindi essere successivamente richiamata tramite l'istanza del delegato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`attrlist`|Facoltativo. Elenco di attributi che si applicano a questo delegato. Gli attributi sono separati da una virgola. È necessario racchiudere il [elenco di attributi](../../../visual-basic/language-reference/statements/attribute-list.md) parentesi angolari ("`<`"e"`>`").|  
|`accessmodifier`|Facoltativo. Specifica il tipo di codice può accedere al delegato. Può essere uno dei seguenti:<br /><br /> - [Pubblica](../../../visual-basic/language-reference/modifiers/public.md). Può accedere qualsiasi codice che possa accedere all'elemento che viene dichiarato il delegato.<br />-   [Protetto](../../../visual-basic/language-reference/modifiers/protected.md). Solo il codice all'interno classe del delegato o una classe derivata può accedervi.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Solo il codice all'interno dello stesso assembly possa accedere al delegato.<br />- [Privato](../../../visual-basic/language-reference/modifiers/private.md). Solo il codice all'interno dell'elemento viene dichiarato il delegato può accedervi.<br /><br /> - [Protected Friend](../../language-reference/modifiers/protected-friend.md) solo codice all'interno dello stesso assembly, una classe derivata o nella classe del delegato può accedere al delegato. <br />- [Private Protected](../../language-reference/modifiers/private-protected.md) solo codice all'interno classe del delegato o in una classe derivata nello stesso assembly può accedere al delegato. |  
|`Shadows`|Facoltativo. Indica che questo delegato ridichiara e nasconde un elemento di programmazione omonimo o un set di elementi in overload, una classe di base. È possibile nascondere qualsiasi tipo di elemento dichiarato con qualsiasi altro tipo.<br /><br /> Un elemento nascosto non è disponibile all'interno della classe derivata che lo nasconde, a meno che l'elemento di shadowing sia inaccessibile. Ad esempio, se un `Private` elemento nasconde un elemento di classe di base, il codice che non dispone dell'autorizzazione per accedere la `Private` elemento accede invece all'elemento di classe di base.|  
|`Sub`|Facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Consente di dichiarare questa routine come delegato `Sub` routine che restituisce un valore.|  
|`Function`|Facoltativo, ma uno `Sub` o `Function` devono essere visualizzati. Consente di dichiarare questa routine come delegato `Function` routine che restituisce un valore.|  
|`name`|Obbligatorio. Nome del tipo delegato. segue le convenzioni di denominazione standard variabile.|  
|`typeparamlist`|Facoltativo. Elenco di parametri di tipo per questo delegato. Più parametri di tipo sono separati da virgole. Facoltativamente, ogni parametro di tipo può essere dichiarato variante mediante `In` e `Out` modificatori generici. È necessario racchiudere il [elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md) racchiuso tra parentesi e introdotte con la `Of` (parola chiave).|  
|`parameterlist`|Facoltativo. Elenco di parametri passati alla procedura quando viene chiamato. È necessario racchiudere il [elenco di parametri](../../../visual-basic/language-reference/statements/parameter-list.md) racchiuso tra parentesi.|  
|`type`|Necessario se si specifica un `Function` procedure. Tipo di dati del valore restituito.|  
  
## <a name="remarks"></a>Note  
 Il `Delegate` istruzione definisce il parametro e tipo restituito di una classe delegata. Qualsiasi routine con parametri e tipi restituiti corrispondenti può essere utilizzato per creare un'istanza di questa classe delegata. La procedura è quindi in un secondo momento accessibile tramite l'istanza del delegato, tramite la chiamata del delegato `Invoke` (metodo).  
  
 I delegati possono essere dichiarati dello spazio dei nomi, modulo, classe o a livello di struttura, ma non all'interno di una procedura.  
  
 Ogni classe delegata definisce un costruttore a cui viene passata la specifica di un metodo dell'oggetto. Un argomento di un costruttore di delegati deve essere un riferimento a un metodo o a un'espressione lambda.  
  
 Per specificare un riferimento a un metodo, usare la sintassi seguente:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Il tipo in fase di compilazione dell'elemento `expression` deve essere il nome di una classe o un'interfaccia contenente un metodo con il nome specificato la cui firma corrisponde a quella della classe delegata. Il metodo `methodname` può essere o un metodo condiviso o un metodo di istanza. `methodname` non è un elemento facoltativo, anche se si crea un delegato per il metodo predefinito della classe.  
  
 Per specificare un'espressione lambda, usare la sintassi seguente:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 La firma della funzione deve corrispondere a quella del tipo delegato. Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda in C++](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Per altre informazioni sui delegati, vedere [delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Delegate` istruzione per dichiarare un delegato per operare su due numeri e la restituzione di un numero. Il `DelegateTest` metodo accetta un'istanza di questo tipo di delegato e lo usa per operare su coppie di numeri.  
  
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
