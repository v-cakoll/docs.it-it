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
ms.openlocfilehash: d1548f7850c68bc3c5422cf9d8d3d30eaa4aa8f3
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035877"
---
# <a name="access-levels-in-visual-basic"></a>Livelli di accesso in Visual Basic

Il *livello di accesso* di un elemento dichiarato è la portata della possibilità di accedervi, ovvero quale codice dispone dell'autorizzazione per la lettura o la scrittura. Questa operazione viene determinata non solo dalla modalità di dichiarazione dell'elemento stesso, ma anche dal livello di accesso del contenitore dell'elemento. Il codice che non può accedere a un elemento contenitore non può accedere ad alcuno degli elementi contenuti, anche quelli dichiarati come `Public`. Ad esempio, è possibile accedere a una variabile `Public` in una struttura `Private` dall'interno della classe che contiene la struttura, ma non dall'esterno di tale classe.

## <a name="public"></a>Public

La parola chiave [public](../../../language-reference/modifiers/public.md) nell'istruzione di dichiarazione specifica che è possibile accedere all'elemento dal codice in qualsiasi punto dello stesso progetto, da altri progetti che fanno riferimento al progetto e da qualsiasi assembly compilato dal progetto. Nel codice seguente viene illustrata una dichiarazione di `Public` di esempio:

```vb
Public Class ClassForEverybody
```

È possibile usare `Public` solo a livello di modulo, interfaccia o spazio dei nomi. Ciò significa che è possibile dichiarare un elemento pubblico a livello di un file di origine o di uno spazio dei nomi o all'interno di un'interfaccia, un modulo, una classe o una struttura, ma non in una procedura.
  
## <a name="protected"></a>Protected

La parola chiave [protected](../../../language-reference/modifiers/protected.md) nell'istruzione di dichiarazione specifica che è possibile accedere all'elemento solo dall'interno della stessa classe o da una classe derivata da questa classe. Nel codice seguente viene illustrata una dichiarazione di `Protected` di esempio:

```vb
Protected Class ClassForMyHeirs
```

È possibile utilizzare `Protected` solo a livello di classe e solo quando si dichiara un membro di una classe. Ciò significa che è possibile dichiarare un elemento protetto in una classe, ma non a livello di un file di origine o di uno spazio dei nomi o all'interno di un'interfaccia, un modulo, una struttura o una procedura.

## <a name="friend"></a>Friend

La parola chiave [Friend](../../../language-reference/modifiers/friend.md) nell'istruzione di dichiarazione specifica che è possibile accedere all'elemento dall'interno dello stesso assembly, ma non dall'esterno dell'assembly. Nel codice seguente viene illustrata una dichiarazione di `Friend` di esempio:

```vb
Friend stringForThisProject As String
```

È possibile usare `Friend` solo a livello di modulo, interfaccia o spazio dei nomi. Ciò significa che è possibile dichiarare un elemento Friend a livello di un file di origine o di uno spazio dei nomi o all'interno di un'interfaccia, un modulo, una classe o una struttura, ma non in una procedura.

## <a name="protected-friend"></a>Protected Friend

La combinazione di parole chiave [Friend protette](../../../language-reference/modifiers/protected-friend.md) nell'istruzione di dichiarazione specifica che è possibile accedere all'elemento dalle classi derivate o dall'interno dello stesso assembly o da entrambi. Nel codice seguente viene illustrata una dichiarazione di `Protected Friend` di esempio:

```vb
Protected Friend stringForProjectAndHeirs As String
```

È possibile utilizzare `Protected Friend` solo a livello di classe e solo quando si dichiara un membro di una classe. Ciò significa che è possibile dichiarare un elemento Friend protetto in una classe, ma non a livello di un file di origine o di uno spazio dei nomi o all'interno di un'interfaccia, un modulo, una struttura o una procedura.

## <a name="private"></a>Private

La parola chiave [private](../../../language-reference/modifiers/private.md) nell'istruzione di dichiarazione specifica che è possibile accedere all'elemento solo dall'interno dello stesso modulo, classe o struttura. Nel codice seguente viene illustrata una dichiarazione di `Private` di esempio:

```vb
Private _numberForMeOnly As Integer
```

Si può usare `Private` solo a livello di modulo. Ciò significa che è possibile dichiarare un elemento privato all'interno di un modulo, una classe o una struttura, ma non a livello di un file di origine o di uno spazio dei nomi, all'interno di un'interfaccia o in una procedura.

A livello di modulo, l'istruzione `Dim` senza parole chiave del livello di accesso equivale a una dichiarazione di `Private`. Tuttavia, potrebbe essere necessario usare la parola chiave `Private` per semplificare la lettura e l'interpretazione del codice.

## <a name="private-protected"></a>Private Protected

La combinazione di parole chiave [privata protetta](../../../language-reference/modifiers/private-protected.md) nell'istruzione di dichiarazione specifica che è possibile accedere all'elemento solo dall'interno della stessa classe, oltre che dalle classi derivate trovate nello stesso assembly della classe che lo contiene. Il modificatore di accesso `Private Protected` è supportato a partire da Visual Basic 15,5.

Nell'esempio seguente viene illustrata una dichiarazione di `Private Protected`:

```vb
Private Protected internalValue As Integer
```

È possibile dichiarare un elemento `Private Protected` solo all'interno di una classe. Non è possibile dichiararlo all'interno di un'interfaccia o di una struttura né dichiararlo a livello di un file di origine o di uno spazio dei nomi, all'interno di un'interfaccia o di una struttura o in una procedura.

Il modificatore di accesso `Private Protected` è supportato da Visual Basic 15,5 e versioni successive. Per usarlo, è necessario aggiungere l'elemento seguente al file del progetto Visual Basic ( *\*. vbproj*). Fino a quando nel sistema è installato Visual Basic 15,5 o versione successiva, è possibile sfruttare tutte le funzionalità del linguaggio supportate dalla versione più recente del compilatore Visual Basic:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Per usare il modificatore di accesso `Private Protected`, è necessario aggiungere l'elemento seguente al file del progetto di Visual Basic ( *\*. vbproj*):

```xml
<PropertyGroup>
   <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Per ulteriori informazioni, vedere [impostazione della versione della lingua Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="access-modifiers"></a>Modificatori di accesso

Le parole chiave che specificano il livello di accesso sono denominate *modificatori di accesso*. Nella tabella seguente vengono confrontati i modificatori di accesso:

|Modificatore di accesso|Livello di accesso concesso|Elementi che è possibile dichiarare con questo livello di accesso|Contesto di dichiarazione in cui è possibile usare questo modificatore|
|---------------------|--------------------------|-----------------------------------------------------|----------------------------------------------------------------|
|`Public`|Illimitato<br /><br /> Qualsiasi codice in grado di visualizzare un elemento pubblico può accedervi|Interfacce<br /><br /> Moduli<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri della struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|File di origine<br /><br /> Spazio dei nomi<br /><br /> Interfaccia<br /><br /> Modulo<br /><br /> Class<br /><br /> Struttura|
|`Protected`|Derivazionali<br /><br /> Il codice nella classe che dichiara un elemento protetto, o una classe derivata, può accedere all'elemento|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Class|
|`Friend`|Assembly:<br /><br /> Il codice nell'assembly che dichiara un elemento Friend può accedervi|Interfacce<br /><br /> Moduli<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri della struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|File di origine<br /><br /> Spazio dei nomi<br /><br /> Interfaccia<br /><br /> Modulo<br /><br /> Class<br /><br /> Struttura|
|`Protected` `Friend`|Unione di `Protected` e `Friend`:<br /><br /> Il codice nella stessa classe o nello stesso assembly di un elemento Friend protetto, o all'interno di una classe derivata dalla classe dell'elemento, può accedervi|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Class|
|`Private`|Contesto di dichiarazione:<br /><br /> Il codice nel tipo che dichiara un elemento privato, incluso il codice all'interno di tipi indipendenti, può accedere all'elemento|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Membri della struttura<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Modulo<br /><br /> Class<br /><br /> Struttura|
|`Private Protected`|Codice della classe che dichiara un elemento protetto privato o codice in una classe derivata presente nello stesso assembly della classe Bas.|Interfacce<br /><br /> Classi<br /><br /> Strutture<br /><br /> Procedure<br /><br /> Proprietà<br /><br /> Variabili membro<br /><br /> Costanti<br /><br /> Enumerazioni<br /><br /> eventi<br /><br /> Dichiarazioni esterne<br /><br /> Delegati|Class|

## <a name="see-also"></a>Vedere anche

- [Istruzione Dim](../../../language-reference/statements/dim-statement.md)
- [Static](../../../language-reference/modifiers/static.md)
- [Nomi di elementi dichiarati](declared-element-names.md)
- [Riferimenti a elementi dichiarati](references-to-declared-elements.md)
- [Caratteristiche di elementi dichiarati](declared-element-characteristics.md)
- [Durata in Visual Basic](lifetime.md)
- [Ambito in Visual Basic](scope.md)
- [Procedura: controllare la disponibilità di una variabile](how-to-control-the-availability-of-a-variable.md)
- [Variabili](../variables/index.md)
- [Dichiarazione di variabile](../variables/variable-declaration.md)
