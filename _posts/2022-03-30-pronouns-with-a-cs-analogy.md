---
title: "Normalize Pronouns"
tags: [classroom climate, pronouns, cs]
description: Explaining pronouns with a CS analogy
author:
    name: Victor Huang
redirect_from: /pronouns-with-a-cs-analogy/
---

Let’s explain pronouns with a CS analogy. We traditionally think of a person as follows:

```java
class Person {
    private String name;
    private boolean isMale;
    
    private Map<String, Boolean> knownPeople;
    
    public String introduceSelf() {
        return name;
    }

    public void meetForFirstTime(Person newPerson) {
        knownPeople.put(newPerson.introduceSelf(), computeGender(newPerson));
    }
    
    /**
     * Based on a set of features of the new person (hair length, body shape,
     * clothing, voice, etc), predicts whether the person is male.
     */
    private boolean computeGender(Person newPerson) {
        // implementation goes here
    }
}
```
While computeGender can yield a very high accuracy, it is almost impossible to get 100%, and it is rather resource-intensive. We can solve this problem by using the ground truth that already exists: have the sender broadcast the relevant information, rather than force the asker to waste compute. Lastly, a person’s pronouns do not necessarily reflect their sex, or even their gender. Using a boolean for a person’s sex (and by proxy, everything else) requires an implicit understanding of what a true and false value means, and subsequent unnecessary translating. We instead will make this explicit with an Enum. This has the added benefit of making it explicit that it is no longer used in common interactions. Backwards compatibility will be an issue, but we expect that the tradeoff will be worth it in the long run. Note that while we could also simply make all the fields public, this has privacy and security concerns, and is not good practice.

```java
class Introduction {
    String name;
    List<String> pronouns;

    public Introduction(String name, List<String> pronouns) {
        this.name = name;
        this.pronouns = new ArrayList<>(pronouns);
    }
}

enum Sex {
    // biologically-classified sexes to be listed here
}

class Person {
    private String name;
    private Sex sex;
    private List<String> pronouns;

    private Map<String, List<String>> knownPeople;

    public Introduction introduceSelf() {
        return new Introduction(name, pronouns);
    }

    public void meetForFirstTime(Person newPerson) {
        Introduction intro = newPerson.introduceSelf();
        knownPeople.put(intro.name, intro.pronouns);
    }
}
```


A person’s pronouns, just like their name, refer to what they would like to be called. When you first learned about pronouns, using “he” or “she” to refer to someone took some adjustment (though, you likely do not remember this because you were likely a small child). Similarly, asking for someone’s pronouns rather than assuming them will take some adjustment.

Lastly, be mindful of the distinction between asking someone what they would like to be called and what they are. To avoid making this mistake in your classroom, you must first internalize this distinction. When asking students for their names and pronouns, you are not categorizing them into genders; instead, you are simply asking them what to call them. For example, consider the following introductions:
- “Hi, my name is Esther. I use she/her pronouns. What’s your name?”
- “Hi, my name is Christopher. I am white. What are you?”

It’s a subtle difference, but what makes the latter so uncomfortable is that it asks the recipient to categorize themselves, rather than simply give their appellation.

Normalizing pronouns in your classroom is as simple as using the new API. When you introduce yourself, include your pronouns. When asking for a student’s name, also ask for their pronouns. The more you practice this process, the more natural it will feel to you, and subsequently, the more comfortable your students will feel sharing their pronouns.

## Third-person singular “they”

Another thing you will want to practice is using “they” to refer to a singular student, either when you do not know their pronouns, or when you want to talk about them without revealing their name. For example, in a staff meeting, you might say, “One of my students had a question I couldn’t answer today. Here’s what they asked: …”. Not only is this faster than “he or she”, it is more inclusive (literally, since the set of all pronouns is not included in “he or she”).

And if it matters to you (or if you find yourself in a discussion with the ~~pedantically~~ grammatically inclined), using “they” to refer to a single person dates back as far as the King James version of the Bible. It is grammatically correct to use “they” as a third-person singular pronoun.
