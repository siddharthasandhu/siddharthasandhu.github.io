---
layout: post
title:  "Setting up Spring in Gradle"
date:   2020-02-10 00:32
categories: Java Gradle Intellij 
---
Setting up my first application in Spring with Swagger:

```java
package com.payments.transactions;

import co.elastic.apm.attach.ElasticApmAttacher;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import springfox.documentation.swagger2.annotations.EnableSwagger2;

@SpringBootApplication
@EnableSwagger2
public class TransactionsApplication {

	public static void main(String[] args) {
		ElasticApmAttacher.attach();
		SpringApplication.run(TransactionsApplication.class, args);
	}
}
```

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[spring-initializer]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
