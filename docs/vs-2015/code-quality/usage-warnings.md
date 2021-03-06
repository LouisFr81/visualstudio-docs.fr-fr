---
title: Avertissements d’utilisation | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.usagerules
helpviewer_keywords:
- warnings, usage
- managed code analysis warnings, usage warnings
- usage warnings
ms.assetid: fe7dc2a3-289d-4bf7-a1e4-0947a81287c4
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 01c6ea3734029879037154e9bad2224f6154ff54
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49238158"
---
# <a name="usage-warnings"></a>avertissements liés à l’utilisation
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Avertissements d’utilisation prend en charge l’utilisation correcte du .NET Framework.  
  
## <a name="in-this-section"></a>Dans cette section  
  
|Règle|Description|  
|----------|-----------------|  
|[CA1801 : Passez en revue les paramètres inutilisés](../code-quality/ca1801-review-unused-parameters.md)|Une signature de méthode inclut un paramètre qui n'est pas utilisé dans le corps de la méthode.|  
|[CA1806 : Ne pas ignorer les résultats de méthode](../code-quality/ca1806-do-not-ignore-method-results.md)|Un nouvel objet est créé mais jamais utilisé ; ou une méthode qui crée et retourne une nouvelle chaîne est appelée et la nouvelle chaîne n'est jamais utilisée ; ou une méthode COM ou P/Invoke retourne un code HRESULT ou d'erreur qui n'est jamais utilisé.|  
|[CA1816 : Appelez GC.SuppressFinalize correctement](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)|Une méthode qui est une implémentation de Dispose n’appelle pas de catalogue global. SuppressFinalize ; ou une méthode qui n’est pas une implémentation de Dispose appelle GC. SuppressFinalize ; ou une méthode appelle GC. SuppressFinalize et passe un élément autre que cette (Me en Visual Basic).|  
|[CA2200 : Levez à nouveau une exception pour conserver les détails de la pile](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)|Une exception est levée de nouveau et l’exception est explicitement spécifiée dans l’instruction throw. Si une exception est levée à nouveau en spécifiant l’exception dans l’instruction throw, la liste d’appels de méthode entre la méthode d’origine qui a levé l’exception et la méthode actuelle est perdue.|  
|[CA2201 : Ne levez pas des types d’exceptions réservés](../code-quality/ca2201-do-not-raise-reserved-exception-types.md)|Cela rend l’erreur d’origine difficile à détecter et à déboguer.|  
|[CA2202 : Ne pas supprimer des objets plusieurs fois](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)|Une implémentation de méthode contient des chemins d’accès de code qui peuvent provoquer des appels multiples à System.IDisposable.Dispose ou un Dispose équivalent (par exemple, une méthode Close() sur certains types) sur le même objet.|  
|[CA2204 : Les littéraux doivent être correctement orthographiés](../code-quality/ca2204-literals-should-be-spelled-correctly.md)|Une chaîne littéral dans un corps de méthode contient un ou plusieurs mots qui ne sont pas reconnus par la bibliothèque de vérificateur d'orthographe Microsoft.|  
|[CA2205 : Utilisez des équivalents managés de l’API Win32](../code-quality/ca2205-use-managed-equivalents-of-win32-api.md)|Un appel de méthode est définie et une méthode avec la fonctionnalité équivalente existe dans la bibliothèque de classes .NET Framework.|  
|[CA2207 : Initialisez les champs statiques des types de valeurs inline](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)|Un type valeur déclare un constructeur statique explicite. Pour corriger une violation de cette règle, initialisez toutes les données statiques lorsqu’elles sont déclarées et supprimez le constructeur statique.|  
|[CA2208 : Instanciez les exceptions d’argument correctement](../code-quality/ca2208-instantiate-argument-exceptions-correctly.md)|Un appel est passé au constructeur par défaut (sans paramètre) d’un type d’exception qui est ou dérive d’ArgumentException, ou un argument string incorrect est passé à un constructeur paramétrable d’un type d’exception qui est ou dérive d’ArgumentException.|  
|[CA2211 : Les champs non constants ne doivent pas être visibles](../code-quality/ca2211-non-constant-fields-should-not-be-visible.md)|Les champs static qui ne sont ni constants ni en lecture seule ne sont pas thread-safe. Accès à un tel champ doit être scrupuleusement contrôlé et nécessite des techniques de programmation évoluées pour synchroniser l’accès à l’objet de classe.|  
|[CA2212 : Ne marquez pas les composants pris en charge avec WebMethod](../code-quality/ca2212-do-not-mark-serviced-components-with-webmethod.md)|Une méthode dans un type qui hérite de System.EnterpriseServices.ServicedComponent est marquée avec System.Web.Services.WebMethodAttribute. Sachant que WebMethodAttribute et une méthode ServicedComponent ont des comportements incompatibles et des exigences en matière de contexte et de flux de transactions, le comportement de la méthode est incorrect dans certains scénarios.|  
|[CA2213 : Les champs pouvant être supprimés doivent l’être](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|Un type qui implémente System.IDisposable déclare des champs de types qui implémentent également IDisposable. La méthode Dispose du champ n’est pas appelée par la méthode Dispose du type déclarant.|  
|[CA2214 : N’appelez pas de méthodes substituables dans les constructeurs](../code-quality/ca2214-do-not-call-overridable-methods-in-constructors.md)|Lorsqu’un constructeur appelle une méthode virtuelle, il est possible que le constructeur pour l’instance qui appelle la méthode n’a pas été exécutée.|  
|[CA2215 : Les méthodes Dispose doivent appeler la méthode Dispose de la classe de base](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)|Si un type hérite d'un type pouvant être supprimé, il doit appeler la méthode Dispose du type de base issu de sa propre méthode Dispose.|  
|[CA2216 : Les types supprimables doivent déclarer un finaliseur](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)|Un type qui implémente System.IDisposable et présente des champs qui laissent entendre l’utilisation des ressources non managées, n’implémente pas de finaliseur comme décrit par Object.Finalize.|  
|[CA2217 : Ne marquez pas les énumérations avec FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)|Une énumération extérieurement visible est marquée par FlagsAttribute et possède une ou plusieurs valeurs qui ne sont pas des puissances de deux ou une combinaison des autres valeurs définies dans l’énumération.|  
|[CA2218 : Remplacez GetHashCode lors du remplacement de Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)|GetHashCode retourne une valeur fondée sur l’instance actuelle adaptée aux algorithmes de hachage et aux structures de données telles qu’une table de hachage. Deux objets de même type et égaux doivent retourner le même code de hachage.|  
|[CA2219 : Ne levez pas d’exceptions dans les clauses d’exception](../code-quality/ca2219-do-not-raise-exceptions-in-exception-clauses.md)|Lorsqu'une exception est levée dans une clause finally ou fault, la nouvelle exception masque l'exception active. Lorsqu'une exception est levée dans une clause filter, le runtime l'intercepte en silence. Cela rend l’erreur d’origine difficile à détecter et à déboguer.|  
|[CA2220 : Les finaliseurs doivent appeler le finaliseur de la classe de base](../code-quality/ca2220-finalizers-should-call-base-class-finalizer.md)|La finalisation doit être propagée par le biais de la hiérarchie d'héritage. Pour garantir ce procédé, les types doivent appeler leur méthode Finalize de classe de base à partir de leur propre méthode Finalize.|  
|[CA2221 : Les finaliseurs doivent être protégés](../code-quality/ca2221-finalizers-should-be-protected.md)|Les finaliseurs doivent utiliser le modificateur d’accès family.|  
|[CA2222 : Ne réduisez pas la visibilité des membres hérités](../code-quality/ca2222-do-not-decrease-inherited-member-visibility.md)|Vous ne devez pas modifier le modificateur d’accès destiné aux membres hérités. La modification d'un membre hérité au profit d'un état privé n'empêche pas les appelants d'accéder à l'implémentation de classe de base de la méthode.|  
|[CA2223 : Les membres ne doivent pas différer uniquement par leur type de retour](../code-quality/ca2223-members-should-differ-by-more-than-return-type.md)|Bien que le Common Language Runtime autorise l’utilisation de types de retour pour différencier des membres autrement identiques, cette fonctionnalité ne figure pas dans la Common Language Specification, et n’est pas une fonctionnalité courante des langages de programmation .NET.|  
|[CA2224 : Remplacez Equals lors de la surcharge de l’opérateur égal](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)|Un type public implémente l’opérateur d’égalité, mais ne substitue pas Object.Equals.|  
|[CA2225 : Les surcharges d’opérateur ont d’autres méthodes nommées](../code-quality/ca2225-operator-overloads-have-named-alternates.md)|Une surcharge d'opérateur a été détectée, et la méthode de substitution nommée attendue n'a pas été trouvée. Le membre de substitution nommé donne accès à la même fonctionnalité que l’opérateur et est fourni pour les développeurs qui programment dans les langages qui ne prennent pas en charge les opérateurs surchargés.|  
|[CA2226 : Les opérateurs doivent avoir des surcharges symétriques](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)|Un type implémente l’égalité ou l’opérateur d’inégalité et n’implémente pas l’opérateur opposé.|  
|[CA2227 : Les propriétés de collection doivent être en lecture seule](../code-quality/ca2227-collection-properties-should-be-read-only.md)|Une propriété de collection accessible en écriture permet à un utilisateur de remplacer la collection par une collection différente. Une propriété en lecture seule empêche le remplacement de la collection, mais permet quand même aux membres individuels d’être définis.|  
|[CA2228 : Ne distribuez pas des formats de ressources non commercialisés](../code-quality/ca2228-do-not-ship-unreleased-resource-formats.md)|Les fichiers de ressources qui ont été créés à l’aide de versions préliminaires du .NET Framework n’est peut-être pas utilisables par les versions prises en charge du .NET Framework.|  
|[CA2229 : Implémentez des constructeurs de sérialisation](../code-quality/ca2229-implement-serialization-constructors.md)|Pour corriger une violation de cette règle, implémentez le constructeur de sérialisation. Dans le cas d'une classe sealed, rendez le constructeur privé ; sinon, attribuez-lui l'état protégé.|  
|[CA2230 : Utilisez le mot clé params pour les arguments de variables](../code-quality/ca2230-use-params-for-variable-arguments.md)|Un type public ou protégé contient une méthode publique ou protégée qui utilise la convention d’appel VarArgs au lieu du mot clé params.|  
|[CA2231 : Surchargez l’opérateur égal (equals) en remplaçant ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|Un type valeur se substitue à Object.Equals mais n'implémente pas l'opérateur d'égalité.|  
|[CA2232 : Marquez les points d’entrée Windows Forms avec STAThread](../code-quality/ca2232-mark-windows-forms-entry-points-with-stathread.md)|STAThreadAttribute indique que le modèle de thread COM pour l'application est un thread cloisonné (STA, Single-Threaded Apartment). Cet attribut doit être présent au point d'entrée de toute application qui utilise des Windows Forms ; s'il est omis, les composants Windows peuvent ne pas fonctionner correctement.|  
|[CA2233 : Les opérations ne doivent pas provoquer de dépassement de capacité](../code-quality/ca2233-operations-should-not-overflow.md)|Opérations arithmétiques ne doivent pas être effectuées sans valider au préalable les opérandes, pour vous assurer que le résultat de l’opération n’est pas en dehors de la plage de valeurs possibles pour les types de données impliqués.|  
|[CA2234 : Passez des objets System.Uri au lieu de chaînes](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)|Un appel est passé à une méthode qui a un paramètre de chaîne dont le nom contient « uri », « URI », « urn », « URN », « url » ou « URL ».  Le type déclarant de la méthode contient une surcharge de méthode correspondante qui a un paramètre System.Uri.|  
|[CA2235 : Marquez tous les champs non sérialisables](../code-quality/ca2235-mark-all-non-serializable-fields.md)|Un champ d'instance d'un type non sérialisable est déclaré dans un type sérialisable.|  
|[CA2236 : Appelez les méthodes de la classe de base sur les types ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)|Pour corriger une violation de cette règle, appelez la méthode GetObjectData ou le constructeur de sérialisation du type de base issu du constructeur ou de la méthode du type dérivé correspondant.|  
|[CA2237 : Marquez les types ISerializable avec SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)|Pour être reconnus par le common language runtime comme sérialisables, les types doivent être marqués avec l’attribut SerializableAttribute même si le type utilise une routine de sérialisation personnalisée via l’implémentation de l’interface ISerializable.|  
|[CA2238 : Implémentez les méthodes de sérialisation correctement](../code-quality/ca2238-implement-serialization-methods-correctly.md)|Une méthode qui gère un événement de sérialisation n’a pas la signature, le type de retour ou la visibilité appropriée.|  
|[CA2239 : Spécifiez des méthodes de désérialisation pour les champs facultatifs](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)|Un type a un champ qui est marqué avec l’attribut System.Runtime.Serialization.OptionalFieldAttribute et le type ne fournit pas de méthodes de gestion des événements de désérialisation.|  
|[CA2240 : Implémentez ISerializable correctement](../code-quality/ca2240-implement-iserializable-correctly.md)|Pour corriger une violation de cette règle, rendez la méthode GetObjectData visible et substituable et assurez-vous que tous les champs d’instance sont inclus dans le processus de sérialisation ou sont marqués explicitement avec l’attribut NonSerializedAttribute.|  
|[CA2241 : Fournissez des arguments corrects aux méthodes de mise en forme](../code-quality/ca2241-provide-correct-arguments-to-formatting-methods.md)|L’argument de format passé à System.String.Format ne contient pas un élément de format qui correspond à chaque argument d’objet, ou vice versa.|  
|[CA2242 : Effectuez correctement des tests NaN](../code-quality/ca2242-test-for-nan-correctly.md)|Cette expression teste une valeur par rapport à Single.Nan ou Double.Nan. Utilisez Single.IsNan(Single) ou Double.IsNan(Double) pour tester la valeur.|  
|[CA2243 : Les littéraux de chaîne d’attribut doivent être analysés correctement](../code-quality/ca2243-attribute-string-literals-should-parse-correctly.md)|Paramètre de littéral de chaîne d’un attribut n’analyse pas correctement pour une URL, un GUID ou une version.|



