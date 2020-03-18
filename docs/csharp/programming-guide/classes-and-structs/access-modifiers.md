---
title: Modificatori di accesso - Guida per programmatori C#
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 749d53344a2518966cfa5d937069ba73dfd6be8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628228"
---
# <a name="access-modifiers-c-programming-guide"></a>Modificatori di accesso (Guida per programmatori C#)

Tutti i tipi e i membri dei tipi hanno un livello di accessibilità. Il livello di accessibilità controlla se possono essere utilizzati da altro codice nell'assembly o in altri assembly. Utilizzare i modificatori di accesso seguenti per specificare l'accessibilità di un tipo o di un membro quando viene dichiarato:

- [public](../../language-reference/keywords/public.md): il tipo o il membro è accessibile da qualsiasi altro codice nello stesso assembly o in un altro assembly che vi fa riferimento.
- [private](../../language-reference/keywords/private.md): il tipo o il membro è `class` `struct`accessibile solo dal codice nello stesso oggetto o .
- [protected](../../language-reference/keywords/protected.md): il tipo o il membro è `class`accessibile `class` solo dal codice `class`nello stesso oggetto o in un oggetto derivato da tale .
- [internal](../../language-reference/keywords/internal.md): il tipo o il membro è accessibile da qualsiasi codice nello stesso assembly, ma non da un altro assembly.
- [protected internal](../../language-reference/keywords/protected-internal.md): Il tipo o il membro è accessibile da qualsiasi codice nell'assembly in cui è dichiarato o dall'interno di un oggetto derivato `class` in un altro assembly.
- [private protected](../../language-reference/keywords/private-protected.md): è possibile accedere al tipo o al membro `class` solo all'interno del relativo assembly dichiarante, dal codice nello stesso o in un tipo derivato da tale `class`.

L'esempio seguente illustra come specificare i modificatori di accesso in un tipo e in un membro:

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

Non tutti i modificatori di accesso sono validi per tutti i tipi o membri in tutti i contesti. In alcuni casi, l'accessibilità di un membro del tipo è vincolata dall'accessibilità del tipo che lo contiene.

## <a name="class-and-struct-accessibility"></a>Accessibilità di classi e struct  

Le classi e gli struct dichiarati direttamente all'interno di uno spazio dei nomi `public` (in altre parole, che non sono annidati all'interno di altre classi o struct) possono essere o `internal`. `Internal`è l'impostazione predefinita se non viene specificato alcun modificatore di accesso.  

I membri struct, incluse le classi `public`e `internal`gli `private`struct annidati, possono essere dichiarati , , o . I membri di classe, incluse le `public` `protected internal`classi `protected` `internal`e `private protected`gli `private`struct annidati, possono essere , , , , , o . I membri di classe e struct, `private` incluse le classi e gli struct annidati, hanno accesso per impostazione predefinita. I tipi annidati privati non sono accessibili dall'esterno del tipo che lo contiene.

Le classi derivate non possono avere maggiore accessibilità rispetto ai relativi tipi di base. Non è possibile dichiarare `B` una classe pubblica che `A`deriva da una classe interna. Se consentito, avrebbe l'effetto di `A` rendere pubblico, perché tutti `protected` o `internal` i membri di `A` sono accessibili dalla classe derivata.

È possibile abilitare altri assembly specifici per `InternalsVisibleToAttribute`accedere ai tipi interni utilizzando il metodo . Per ulteriori informazioni, vedere [Assembly Friend](../../../standard/assembly/friend.md).

## <a name="class-and-struct-member-accessibility"></a>Accessibilità dei membri di classe e struct  

I membri di classe (inclusi le classi e gli struct annidati) possono essere dichiarati con uno qualsiasi dei sei tipi di accesso. I membri struct non `protected`possono `protected internal`essere `private protected` dichiarati come , , o perché gli struct non supportano l'ereditarietà.

In genere, l'accessibilità di un membro non è maggiore dell'accessibilità del tipo che lo contiene. Tuttavia, `public` un membro di una classe interna potrebbe essere accessibile dall'esterno dell'assembly se il membro implementa metodi di interfaccia o esegue l'override di metodi virtuali definiti in una classe base pubblica.

Il tipo di qualsiasi campo membro, proprietà o evento deve essere accessibile almeno quanto il membro stesso. Analogamente, il tipo restituito e i tipi di parametro di qualsiasi metodo, indicizzatore o delegato devono essere accessibili almeno quanto il membro stesso. Ad esempio, non è `public` possibile `M` avere un `C` `C` metodo `public`che restituisce una classe a meno che non sia anche . Analogamente, non è `protected` possibile avere `A` `A` una proprietà `private`di tipo se viene dichiarato come .

Gli operatori definiti dall'utente `public` `static`devono sempre essere dichiarati come e . Per altre informazioni, vedere [Overload degli operatori](../../language-reference/operators/operator-overloading.md).

I finalizzatori non possono avere modificatori di accessibilità.

Per impostare il `class` livello `struct` di accesso per un membro o, aggiungere la parola chiave appropriata alla dichiarazione del membro, come illustrato nell'esempio seguente.

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a>Altri tipi

Le interfacce dichiarate direttamente `public` `internal` all'interno di uno spazio dei nomi `internal` possono essere o e, proprio come le classi e gli struct, le interfacce per impostazione predefinita per l'accesso. I membri `public` di interfaccia sono per impostazione predefinita perché lo scopo di un'interfaccia è consentire ad altri tipi di accedere a una classe o a uno struct. Le dichiarazioni dei membri di interfaccia possono includere qualsiasi modificatore di accesso. Ciò è particolarmente utile per i metodi statici per fornire implementazioni comuni necessarie per tutti gli implementatori di una classe.

I membri `public`di enumerazione sono sempre e non è possibile applicare modificatori di accesso.

I delegati si comportano come classi e struct. Per impostazione `internal` predefinita, hanno accesso quando `private` vengono dichiarati direttamente all'interno di uno spazio dei nomi e quando sono annidati.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Interfacce](../interfaces/index.md)
- [Privato](../../language-reference/keywords/private.md)
- [pubblico](../../language-reference/keywords/public.md)
- [Interno](../../language-reference/keywords/internal.md)
- [Protetto](../../language-reference/keywords/protected.md)
- [protected internal](../../language-reference/keywords/protected-internal.md)
- [private protected](../../language-reference/keywords/private-protected.md)
- [Classe](../../language-reference/keywords/class.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [Interfaccia](../../language-reference/keywords/interface.md)
