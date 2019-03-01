---
title: Livelli di accesso in Visual Basic
ms.date: 05/10/2018
helpviewer_keywords:
- members [Visual Basic], accessing in Visual Basic
- Friend access modifier
- access levels, declared elements
- access levels
- access modifiers
- Public access modifier
- Protected access modifier
- Protected Friend access modifier
- Private Protected access modifier
- Private access modifier
- declared elements [Visual Basic], access level
ms.assetid: 6e06c1ab-fd78-47f0-83a8-1152780b5e1a
ms.openlocfilehash: 1278119ca82678267aa782f2518ab26b50966730
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203626"
---
# <a name="access-levels-in-visual-basic"></a>Livelli di accesso in Visual Basic
Il *livello di accesso* di un elemento dichiarato è l'extent della possibilità di accedervi, vale a dire, il tipo di codice dispone dell'autorizzazione di lettura o scrittura. Ciò è determinato non solo dal modo in cui si dichiara l'elemento stesso, ma anche dal livello di accesso del contenitore dell'elemento. Il codice che non è possibile accedere a un elemento contenitore non può accedere a uno qualsiasi dei relativi elementi contenuti, anche quelli dichiarati come `Public`. Ad esempio, un `Public` di una variabile in un `Private` struttura sono accessibili all'interno della classe che contiene la struttura, ma non all'esterno di tale classe.  
  
## <a name="public"></a>Public  
 Il [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento sia accessibile dal codice in qualsiasi punto nello stesso progetto, da altri progetti che fanno riferimento al progetto e da qualsiasi assembly compilato dal progetto. Il codice seguente illustra un esempio `Public` dichiarazione.  
  
```vb  
Public Class classForEverybody  
```  
  
 È possibile usare `Public` solo a livello di modulo, interfaccia o dello spazio dei nomi. Ciò significa che è possibile dichiarare un elemento pubblico a livello di un file di origine o di spazio dei nomi, o all'interno di un'interfaccia, modulo, classe o struttura, ma non in una routine.  
  
## <a name="protected"></a>Protetta  
 Il [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento è accessibile solo dall'interno della stessa classe o da una classe derivata da questa classe. Il codice seguente illustra un esempio `Protected` dichiarazione.  
  
```vb  
Protected Class classForMyHeirs  
```  
  
 È possibile usare `Protected` solo alla classe di livello e solo quando si dichiara un membro di una classe. Ciò significa che è possibile dichiarare un elemento protetto in una classe, ma non a livello di un file di origine o di spazio dei nomi o all'interno di un'interfaccia, modulo, struttura o procedura.  
  
## <a name="friend"></a>Friend  
 Il [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento sia accessibile dall'interno dello stesso assembly, ma non dall'esterno dell'assembly. Il codice seguente illustra un esempio `Friend` dichiarazione.  
  
```vb  
Friend stringForThisProject As String  
```  
  
 È possibile usare `Friend` solo a livello di modulo, interfaccia o dello spazio dei nomi. Ciò significa che è possibile dichiarare il livello di un file di origine o di spazio dei nomi, o all'interno di un'interfaccia, modulo, classe o struttura, ma non in una routine di un elemento friend.  
  
## <a name="protected-friend"></a>Protected Friend  
 Il [Protected Friend](../../../language-reference/modifiers/protected-friend.md) combinazione di parole chiave nell'istruzione di dichiarazione specifica che l'elemento è accessibile dalle classi derivate o dall'interno dello stesso assembly o entrambi. Il codice seguente illustra un esempio `Protected Friend` dichiarazione.  
  
```vb  
Protected Friend stringForProjectAndHeirs As String  
```  
  
 È possibile usare `Protected Friend` solo alla classe di livello e solo quando si dichiara un membro di una classe. Ciò significa che è possibile dichiarare un elemento protected friend in una classe, ma non a livello di un file di origine o di spazio dei nomi o all'interno di un'interfaccia, modulo, struttura o procedura.  
  
## <a name="private"></a>Private  
 Il [privato](../../../../visual-basic/language-reference/modifiers/private.md) parola chiave nell'istruzione di dichiarazione specifica che l'elemento sono accessibili solo dal modulo, classe o struttura stessa. Il codice seguente illustra un esempio `Private` dichiarazione.  
  
```vb  
Private numberForMeOnly As Integer  
```  
  
 Si può usare `Private` solo a livello di modulo. Ciò significa che è possibile dichiarare un elemento privato all'interno di un modulo, classe o struttura, ma non a livello di un file di origine o di spazio dei nomi, all'interno di un'interfaccia o in una procedura.  
  
 A livello di modulo, il `Dim` istruzione senza eventuali parole chiave a livello di accesso è equivalente a un `Private` dichiarazione. Tuttavia, si potrebbe voler usare il `Private` (parola chiave) per rendere più facile da leggere e interpretare il codice.  

## <a name="private-protected"></a>Private Protected

Il [Private Protected](../../../language-reference/modifiers/private-protected.md) combinazione di parole chiave nell'istruzione di dichiarazione specifica che l'elemento sia accessibile solo dall'interno della stessa classe, nonché dalle classi derivate trovate nello stesso assembly come classe che lo contiene. Il `Private Protected` modificatore di accesso è supportato a partire da Visual Basic 15.5.

L'esempio seguente mostra un `Private Protected` dichiarazione:

```vb
Private Protected internalValue As Integer
```

È possibile dichiarare un `Private Protected` elemento solo all'interno di una classe. Non è possibile dichiarare all'interno di un'interfaccia o struttura, né può è dichiarare viene a livello di un file di origine o spazio dei nomi, all'interno di un'interfaccia o una struttura o in una procedura.

Il `Private Protected` modificatore di accesso è supportato da Visual Basic 15.5 e versioni successive. Per usarla, aggiungere l'elemento seguente al file di progetto (*. vbproj) di Visual Basic. Tempo come Visual Basic 15.5 o versione successiva è installato nel sistema, consente di sfruttare i vantaggi di tutte le funzionalità di linguaggio supportati dalla versione più recente del compilatore Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Usare il `Private Protected` modificatore di accesso, è necessario aggiungere l'elemento seguente al file di progetto (*. vbproj) di Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Per altre informazioni, vedere [impostando la versione del linguaggio Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="access-modifiers"></a>Modificatori di accesso  

Le parole chiave che specificano il livello di accesso vengono chiamate *modificatori di accesso*. La tabella seguente confronta i modificatori di accesso.  
  
|Modificatore di accesso|Livello di accesso concesso|Elementi che è possibile dichiarare con questo livello di accesso|Contesto della dichiarazione all'interno del quale è possibile utilizzare questo modificatore|  
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|  
|`Public`|Senza restrizioni:<br /><br /> Può accedere qualsiasi codice che è possibile visualizzare un elemento pubblico|Interfacce<br /><br /> Moduli<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri di struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|File di origine<br /><br /> Spazio dei nomi<br /><br /> Interfaccia<br /><br /> Modulo<br /><br /> Classe<br /><br /> Struttura|  
|`Protected`|Derivazionali:<br /><br /> Nella classe che dichiara un elemento protetto, o una classe derivata da esso, è possibile accedere all'elemento di codice|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Classe|  
|`Friend`|Assembly:<br /><br /> Nell'assembly che dichiara che un elemento friend relativi diritti di accesso di codice|Interfacce<br /><br /> Moduli<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri di struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|File di origine<br /><br /> Spazio dei nomi<br /><br /> Interfaccia<br /><br /> Modulo<br /><br /> Classe<br /><br /> Struttura|  
|`Protected` `Friend`|Unione di `Protected` e `Friend`:<br /><br /> Il codice nella stessa classe o lo stesso assembly come un elemento protected friend o all'interno di qualsiasi classe derivata dalla classe dell'elemento accesso è consentito.|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Classe|  
|`Private`|Contesto della dichiarazione:<br /><br /> L'elemento accessibile dal codice nel tipo che dichiara un elemento privato, incluso il codice dei tipi contenuti.|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri di struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Modulo<br /><br /> Classe<br /><br /> Struttura|
|`Private Protected`|Il codice della classe che dichiara un elemento protetto privato o codice in una classe derivata trovato nello stesso assembly della classe di bas.|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> Eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Classe|
  
## <a name="see-also"></a>Vedere anche
- [Istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Riferimenti a elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Procedura: Controllare la disponibilità di una variabile](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md)
- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
