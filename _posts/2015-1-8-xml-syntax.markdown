---
layout: post
title:  "Sample of XML Syntax"
date:   2015-1-8 19:15:30 +0700
categories: jekyll update
---
Here are an example of how writing an XML code snippets for Semantic purposes. Quite simple, actually. This sample is depicted from Jeff Pollock's book `Semantic Web for Dummies`. A good book for starting in studying semantic web.

{% highlight xml %}
<?xml version=”1.0”?>
<rdf:RDF xmlns:rdf=
	”http://www.w3.org/1999/02/22-rdf-syntax-ns#”
	xmlns:book=”http://www.dummies.com/books#”
	xmlns:dc=”http://purl.org/dc/elements/1.1/”
	xmlns:foaf=”http://xmlns.com/foaf/0.1/”>
	<rdf:Description rdf:about=
		”http://www.dummies.com/books#Book-semanticweb_for_dummies”>
		<book:author rdf:resource=
			”http://me.jtpollock.us/foaf.rdf#me”/>
		<dc:title>The Semantic Web For Dummies</dc:title>
	</rdf:Description>
</rdf:RDF>
{% endhighlight%}