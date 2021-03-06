---
title: "The Queueing Knee, Part 1"
date: 2016-11-30T22:02:08-05:00
url: /blog/queueing-knee-tangent/
description: "The knee in the queueing response time curve illustrates important truths about queueing theory."
credit: "https://unsplash.com/photos/K67sBVqLLuw"
image: "/media/2016/11/unsplash-photos-K67sBVqLLuw.jpg"
thumbnail: /media/2016/11/unsplash-photos-K67sBVqLLuw.tn-500x500.jpg
categories:
- Scalability
- Math
---

The "knee" in the [M/M/m queueing theory response time
curve](/blog/response-time-stretch-factor/) is a topic of some debate in the
performance community. Some say "the knee is at 75% utilization; everyone knows
that." Others say "it depends." Others say "there is no knee."

<!--more-->

Depending on the definition, there _is_ a knee, but there are several
definitions and you may choose the one you want. In this post I'll use a
definition proposed by Cary Millsap: the knee is where a line from the origin is
tangent to the queueing response time curve. The result is a function of the
number of service channels, and although we may argue about the topics in the
preceding paragraph and whether this is the right definition, it still serves to
illustrate important concepts.

![Queueing Delay Knee](/media/2016/11/knee-1.png)

The graph above shows the response time stretch factor curve for a queueing
system with 8 service channels. This is analogous to a server with 8 CPUs, for
example. A line drawn from the origin, tangent to the curve, touches it at
0.7598, or 76% utilization.

The important thing to note is that this curve is a function of {{< math >}}m{{< /math >}}, the
number of service channels. In this case, {{< math >}}m=8{{< /math >}}. As you increase the number
of service channels in the system, the curve remains flat longer and the "knee,"
where the curve appears to lift upwards and start to climb steeply, moves towards
the right---towards higher utilization, signified by {{< math >}}\rho{{< /math >}}.

You can experiment interactively with this, using this [Desmos
calculator](https://www.desmos.com/calculator/cqh81xgspq).[^1]
Here's the derivation. Using the heuristic approximation,

{{< math >}}
R = \frac{1}{1-\rho^m}
{{< /math >}}

The line is tangent to the curve where *response time divided by
utilization* is at a minimum. The equation for {{< math >}}R/\rho{{< /math >}} is

{{< math >}}
R/\rho = \frac{1}{\rho - \rho^{m+1}}
{{< /math >}}

The minimum of this equation is where its derivative is zero; the derivative is

{{< math >}}
\frac{\left(m+1\right)\rho^m-1}{\rho^2\left(\rho^m-1\right)^2}
{{< /math >}}

The root of this expression is a function of {{< math >}}m{{< /math >}} as expected.

{{< math >}}
\left(m+1\right)^{-\frac{1}{m}}
{{< /math >}}

Here's how that function looks when
[plotted](https://www.desmos.com/calculator/lnutkzjitx).

![Knee as a function of m](/media/2016/11/knee-2.png)

The graph shows that as the number of service channels increases,
the knee occurs at increasingly high utilization.

Despite the debate over exactly what the definition of the knee is, this
illustrates two fundamental truths about queueing systems:

1. As you add service channels (servers) to a queueing system, queueing delay is
	tolerable at increasingly high utilization.
2. The heuristic that you can't run a system at greater than 75% utilization
	is invalid. For systems with many service channels (CPUs, disks, etc) that is
	wasteful, and you should strive for higher utilization.

For more on this topic, please read [my free ebook on queueing
theory](https://www.vividcortex.com/resources/queueing-theory).

[^1]: Note that the calculator uses an approximation to the queueing theory response time curve, which is easier to differentiate than the Erlang C formula but underestimates how steeply the curve climbs at higher utilizations. I discussed this heuristic approximation at length in my [previous blog post](/blog/response-time-stretch-factor/). Even though it's an approximation, again, it serves the purposes of this blog post.
