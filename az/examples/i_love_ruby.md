---
layout: nil
---

{% highlight ruby %}
# Çıktı "I love Ruby"
say = "I love Ruby"
puts say

# Çıktı "I *LOVE* RUBY"
say['love'] = "*love*"
puts say.upcase

# Çıktı "I *love* Ruby"
# ama 5 kere
5.times { puts say }
{% endhighlight %}
