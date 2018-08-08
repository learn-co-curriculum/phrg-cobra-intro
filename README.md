# CoBRA

Nitro is built with [CoBRA](http://shageman.github.io/cbra.info/). CoBRA stands for "Component Based Rails Architecture". Instead one gigantic Rails application, Nitro componentizes its overall architecture. CoBRA is a code organization and management technique that breaks large applications into small, distinct parts. This allows for better separation of concerns, dependency management, and ultimately, scalability.

Every Nitro component can be viewed as an application within itself. Nitro components fall into 3 classifications.

1. Ruby Gems
1. Rails Engines
1. Front End

## Ruby Gems

You are very familiar with [Ruby gems](https://guides.rubygems.org/what-is-a-gem/) already. A gem is any Ruby library or application. All gems contain a `gemspec` file that defines its purpose and dependencies. Most gems can be packaged and installed from https://rubygems.org, but a gem does not need to be published. It is simply is a standalone Ruby program.

In Nitro, Ruby gem components do not have databases. And while not a defining feature, most Ruby gem components contain the majority of their logic in their `lib` directories.

Examples of Ruby gem components inside Nitro are:

- `aurora_client`
- `gmaps`
- `naughty`
- `new_relic_event`
- `nitro_auth`
- `nitro_config`
- `nitro_object_store`
- `nitro_redis`
- `ruby_test_helpers`
- `utu_client`

## Rails Engines

[Rails Engines](https://guides.rubyonrails.org/engines.html) are miniature Rails applications. They provide all the functionality of a Rails app, with slightly different configurations. Rails Engines also contain `gemspec`s, which make them Ruby gems as well. One popular Rails Engine is [Devise](https://github.com/plataformatec/devise).

Nitro Rails Engine components typically do not utilize all Rails features. As you gain familiarity with Nitro's structure, you'll find Rails Engine components that use:

1. all MVC classes
1. just Models
1. just Controllers
1. just Views, Controllers, and other supporting user interface objects
1. just Models & Controllers

Examples of Rails Engine components inside Nitro are:

- `adp`
- `call_queues`
- `charitable_giving`
- `contact_center`
- `mobile_devices`
- `outbound_marketing`
- `promos`
- `scrum`
- `solar_roofing`
- `ux_prototypes`

## Front End

Front End components are user interface focused components that typically use the [React](https://reactjs.org/) Javascript framework. You will be learning a lot more about Javascript and the React framework in the coming weeks. For now, remember that you can conceptually think of a Front End component as its own React application.

Examples of React components inside Nitro are:

- `call_queue_ui`
- `contact_center_dashboard`
- `credit_application_ui`
- `home_ui`
- `ops_dashboard`
- `people_ui`
- `promos_ui`
- `scrum_ui`
- `spaces_ui`
- `support_tickets`

## All Components

Regardless of type, there are some standard conventions for every component in Nitro.

1. They all live in the `components/` directory.
1. They all contain a `README.md` with a description of the component's purpose.
1. They all contain a `bin/` directory with executables for setups, builds, and tests.

## Legacy Components

Before Nitro used componentization, it was one gigantic Rails application. As we transitioned into using CoBRA, we started breaking out the most obvious divisions of functionality. Today, anytime a new feature gets added to Nitro, it starts as a new component.

However, there is still a lot of older and essential Nitro functionality that has yet to be componentized. This legacy code lives in our two largest components.

1. `core_models` - Nitro's legacy Models
1. `nitro_component_transition` - Nitro's legacy Controllers & Views

Adding new code into these components should be avoided. Any chance one has to break out some legacy functionality into another component, it should be discussed as a team and pursued if possible. This is not always an easy undertaking, so remember to utilize the support of more senior Nitro developers.

## Resources

- [CoBRA](http://shageman.github.io/cbra.info/)
- [Ruby Gems](https://guides.rubygems.org/what-is-a-gem/)
- [Rails Engines](https://guides.rubyonrails.org/engines.html)
